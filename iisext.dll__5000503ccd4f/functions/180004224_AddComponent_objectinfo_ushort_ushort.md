# AddComponent(_objectinfo *,ushort *,ushort *)

- ea: `0x180004224`
- end: `0x1800042fd`
- name: `?AddComponent@@YAJPEAU_objectinfo@@PEAG1@Z`
- size: `217`
- prototype: `int(struct _objectinfo *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004628`

## callees

- `0x180004224`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsMem` at `0x18000425c`
- `ACTIVEDS!__imp_AllocADsMem` at `0x18000425c`
- `ACTIVEDS!__imp_ReallocADsMem` at `0x180004284`
- `ACTIVEDS!__imp_ReallocADsMem` at `0x180004284`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800042a1`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800042c3`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800042a1`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800042c3`

## pseudocode

```c
__int64 __fastcall AddComponent(struct _objectinfo *a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  void *v6; // rcx
  LPVOID v7; // rax
  _DWORD *v8; // rdi
  int v9; // edx

  if ( !a2 || !*a2 )
    return 2147500037LL;
  v6 = (void *)*((_QWORD *)a1 + 4);
  if ( v6 )
  {
    v9 = *((_DWORD *)a1 + 6);
    v8 = (_DWORD *)((char *)a1 + 20);
    if ( *((_DWORD *)a1 + 5) != v9 )
      goto LABEL_10;
    v7 = ReallocADsMem(v6, 16 * v9, 16 * v9 + 512);
    if ( !v7 )
      return 2147942414LL;
    *((_DWORD *)a1 + 6) += 32;
  }
  else
  {
    v7 = AllocADsMem(0x200u);
    *((_DWORD *)a1 + 6) = 32;
    v8 = (_DWORD *)((char *)a1 + 20);
  }
  *((_QWORD *)a1 + 4) = v7;
LABEL_10:
  *(_QWORD *)(*((_QWORD *)a1 + 4) + 16LL * (unsigned int)*v8) = AllocADsStr(a2);
  if ( a3 && *a3 )
    *(_QWORD *)(*((_QWORD *)a1 + 4) + 16LL * (unsigned int)*v8 + 8) = AllocADsStr(a3);
  else
    *(_QWORD *)(*((_QWORD *)a1 + 4) + 16LL * (unsigned int)*v8 + 8) = 0;
  ++*v8;
  return 0;
}

```

## disassembly

```asm
0x180004224  push    rbx
0x180004226  push    rbp
0x180004227  push    rsi
0x180004228  push    rdi
0x180004229  push    r14
0x18000422b  sub     rsp, 20h
0x18000422f  xor     r14d, r14d
0x180004232  mov     rbp, r8
0x180004235  mov     rsi, rdx
0x180004238  mov     rbx, rcx
0x18000423b  test    rdx, rdx
0x18000423e  jz      loc_1800042ED
0x180004244  cmp     [rdx], r14w
0x180004248  jz      loc_1800042ED
0x18000424e  mov     rcx, [rcx+20h]; pOldMem
0x180004252  test    rcx, rcx
0x180004255  jnz     short loc_18000426F
0x180004257  mov     ecx, 200h; cb
0x18000425c  call    cs:__imp_AllocADsMem
0x180004262  mov     dword ptr [rbx+18h], 20h ; ' '
0x180004269  lea     rdi, [rbx+14h]
0x18000426d  jmp     short loc_18000429A
0x18000426f  mov     edx, [rbx+18h]
0x180004272  lea     rdi, [rbx+14h]
0x180004276  cmp     [rdi], edx
0x180004278  jnz     short loc_18000429E
0x18000427a  shl     edx, 4; cbOld
0x18000427d  lea     r8d, [rdx+200h]; cbNew
0x180004284  call    cs:__imp_ReallocADsMem
0x18000428a  test    rax, rax
0x18000428d  jnz     short loc_180004296
0x18000428f  mov     eax, 8007000Eh
0x180004294  jmp     short loc_1800042F2
0x180004296  add     dword ptr [rbx+18h], 20h ; ' '
0x18000429a  mov     [rbx+20h], rax
0x18000429e  mov     rcx, rsi; pStr
0x1800042a1  call    cs:__imp_AllocADsStr
0x1800042a7  mov     edx, [rdi]
0x1800042a9  mov     rcx, [rbx+20h]
0x1800042ad  add     rdx, rdx
0x1800042b0  mov     [rcx+rdx*8], rax
0x1800042b4  test    rbp, rbp
0x1800042b7  jz      short loc_1800042D9
0x1800042b9  cmp     [rbp+0], r14w
0x1800042be  jz      short loc_1800042D9
0x1800042c0  mov     rcx, rbp; pStr
0x1800042c3  call    cs:__imp_AllocADsStr
0x1800042c9  mov     edx, [rdi]
0x1800042cb  mov     rcx, [rbx+20h]
0x1800042cf  add     rdx, rdx
0x1800042d2  mov     [rcx+rdx*8+8], rax
0x1800042d7  jmp     short loc_1800042E7
0x1800042d9  mov     ecx, [rdi]
0x1800042db  mov     rax, [rbx+20h]
0x1800042df  add     rcx, rcx
0x1800042e2  mov     [rax+rcx*8+8], r14
0x1800042e7  inc     dword ptr [rdi]
0x1800042e9  xor     eax, eax
0x1800042eb  jmp     short loc_1800042F2
0x1800042ed  mov     eax, 80004005h
0x1800042f2  add     rsp, 20h
0x1800042f6  pop     r14
0x1800042f8  pop     rdi
0x1800042f9  pop     rsi
0x1800042fa  pop     rbp
0x1800042fb  pop     rbx
0x1800042fc  retn
```
