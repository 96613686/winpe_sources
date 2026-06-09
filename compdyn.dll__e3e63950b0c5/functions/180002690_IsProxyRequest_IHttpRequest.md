# IsProxyRequest(IHttpRequest *)

- ea: `0x180002690`
- end: `0x180002736`
- name: `?IsProxyRequest@@YAHPEAVIHttpRequest@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(struct IHttpRequest *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001eb0`

## callees

- `0x180002690`
- `0x180008010`

## pseudocode

```c
__int64 __fastcall IsProxyRequest(struct IHttpRequest *a1)
{
  _BYTE *v2; // rax
  _BYTE *v3; // rdx
  char v5; // cl
  unsigned __int16 v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = 0;
  if ( !(*(__int64 (__fastcall **)(struct IHttpRequest *, __int64, _QWORD))(*(_QWORD *)a1 + 16LL))(a1, 8, 0)
    && !(*(__int64 (__fastcall **)(struct IHttpRequest *, const char *, _QWORD))(*(_QWORD *)a1 + 24LL))(
          a1,
          "Forward",
          0) )
  {
    v2 = (_BYTE *)(*(__int64 (__fastcall **)(struct IHttpRequest *, __int64, unsigned __int16 *))(*(_QWORD *)a1 + 16LL))(
                    a1,
                    40,
                    &v6);
    if ( !v2 )
      return 0;
    v3 = &v2[v6 - 3];
    if ( v2 >= v3 )
      return 0;
    while ( 1 )
    {
      if ( ((*v2 - 86) & 0xDF) == 0 && v2[1] == 105 && v2[2] == 97 )
      {
        v5 = v2[3];
        if ( v5 == 32 || v5 == 58 )
          break;
      }
      if ( ++v2 >= v3 )
        return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180002690  push    rbx
0x180002692  sub     rsp, 20h
0x180002696  xor     eax, eax
0x180002698  xor     r8d, r8d
0x18000269b  mov     [rsp+28h+arg_0], ax
0x1800026a0  mov     edx, 8
0x1800026a5  mov     rax, [rcx]
0x1800026a8  mov     rbx, rcx
0x1800026ab  mov     rax, [rax+10h]
0x1800026af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026b4  test    rax, rax
0x1800026b7  jnz     short loc_18000272F
0x1800026b9  mov     rax, [rbx]
0x1800026bc  lea     rdx, aForward; "Forward"
0x1800026c3  xor     r8d, r8d
0x1800026c6  mov     rcx, rbx
0x1800026c9  mov     rax, [rax+18h]
0x1800026cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026d2  test    rax, rax
0x1800026d5  jnz     short loc_18000272F
0x1800026d7  mov     rax, [rbx]
0x1800026da  lea     r8, [rsp+28h+arg_0]
0x1800026df  mov     edx, 28h ; '('
0x1800026e4  mov     rcx, rbx
0x1800026e7  mov     rax, [rax+10h]
0x1800026eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026f0  test    rax, rax
0x1800026f3  jz      short loc_180002727
0x1800026f5  movzx   edx, [rsp+28h+arg_0]
0x1800026fa  add     rdx, 0FFFFFFFFFFFFFFFDh
0x1800026fe  add     rdx, rax
0x180002701  cmp     rax, rdx
0x180002704  jnb     short loc_180002727
0x180002706  nop     word ptr [rax+rax+00000000h]
0x180002710  movzx   ecx, byte ptr [rax]
0x180002713  sub     cl, 56h ; 'V'
0x180002716  test    cl, 0DFh
0x180002719  jz      loc_18000577A
0x18000271f  inc     rax
0x180002722  cmp     rax, rdx
0x180002725  jb      short loc_180002710
0x180002727  xor     eax, eax
0x180002729  add     rsp, 20h
0x18000272d  pop     rbx
0x18000272e  retn
0x18000272f  mov     eax, 1
0x180002734  jmp     short loc_180002729
0x18000577a  cmp     byte ptr [rax+1], 69h ; 'i'
0x18000577e  jnz     loc_18000271F
0x180005784  cmp     byte ptr [rax+2], 61h ; 'a'
0x180005788  jnz     loc_18000271F
0x18000578e  movzx   ecx, byte ptr [rax+3]
0x180005792  cmp     cl, 20h ; ' '
0x180005795  jz      loc_18000272F
0x18000579b  cmp     cl, 3Ah ; ':'
0x18000579e  jz      loc_18000272F
0x1800057a4  jmp     loc_18000271F
```
