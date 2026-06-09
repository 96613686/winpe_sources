# RtdspGenerateEndpointChangelist

- ea: `0x140009340`
- end: `0x140009404`
- name: `RtdspGenerateEndpointChangelist`
- size: `196`
- prototype: `_QWORD *__fastcall(_QWORD **, _QWORD **, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009230`

## callees

- `0x140009340`
- `0x140009830`

## pseudocode

```c
_QWORD *__fastcall RtdspGenerateEndpointChangelist(_QWORD **a1, _QWORD **a2, _QWORD *a3)
{
  _QWORD *i; // rbx
  _QWORD *v7; // rdi
  _QWORD *Endpoint; // rax
  __int64 v9; // rax
  _QWORD *result; // rax
  _QWORD *v11; // rcx
  __int64 v12; // rdx

  a3[1] = a3;
  *a3 = a3;
  for ( i = *a1; i != a1; i = (_QWORD *)*i )
  {
    v7 = i - 5;
    Endpoint = RtdspFindEndpoint(a2, *(i - 2));
    if ( Endpoint )
    {
      *((_DWORD *)Endpoint + 14) = 1;
    }
    else
    {
      *((_DWORD *)v7 + 8) = 2;
      v9 = *a3;
      if ( *(_QWORD **)(*a3 + 8LL) != a3 )
LABEL_13:
        __fastfail(3u);
      *v7 = v9;
      v7[1] = a3;
      *(_QWORD *)(v9 + 8) = v7;
      *a3 = v7;
    }
  }
  for ( result = *a2; result != a2; result = (_QWORD *)*result )
  {
    v11 = result - 5;
    if ( !*((_DWORD *)result + 4) )
    {
      *((_DWORD *)v11 + 8) = 1;
      v12 = *a3;
      if ( *(_QWORD **)(*a3 + 8LL) != a3 )
        goto LABEL_13;
      *v11 = v12;
      v11[1] = a3;
      *(_QWORD *)(v12 + 8) = v11;
      *a3 = v11;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140009340  push    rbx
0x140009342  push    rsi
0x140009343  push    rdi
0x140009344  push    r14
0x140009346  push    r15
0x140009348  sub     rsp, 20h
0x14000934c  mov     [r8+8], r8
0x140009350  mov     r15, r8
0x140009353  mov     [r8], r8
0x140009356  mov     rsi, rdx
0x140009359  mov     rbx, [rcx]
0x14000935c  mov     r14, rcx
0x14000935f  cmp     rbx, rcx
0x140009362  jz      short loc_1400093B4
0x140009364  nop     dword ptr [rax+00h]
0x140009368  nop     dword ptr [rax+rax+00000000h]
0x140009370  mov     rdx, [rbx-10h]
0x140009374  lea     rdi, [rbx-28h]
0x140009378  mov     rcx, rsi
0x14000937b  call    RtdspFindEndpoint
0x140009380  test    rax, rax
0x140009383  jz      short loc_14000938E
0x140009385  mov     dword ptr [rax+38h], 1
0x14000938c  jmp     short loc_1400093AC
0x14000938e  mov     dword ptr [rdi+20h], 2
0x140009395  mov     rax, [r15]
0x140009398  cmp     [rax+8], r15
0x14000939c  jnz     short loc_1400093FD
0x14000939e  mov     [rdi], rax
0x1400093a1  mov     [rdi+8], r15
0x1400093a5  mov     [rax+8], rdi
0x1400093a9  mov     [r15], rdi
0x1400093ac  mov     rbx, [rbx]
0x1400093af  cmp     rbx, r14
0x1400093b2  jnz     short loc_140009370
0x1400093b4  mov     rax, [rsi]
0x1400093b7  cmp     rax, rsi
0x1400093ba  jz      short loc_1400093F0
0x1400093bc  nop     dword ptr [rax+00h]
0x1400093c0  cmp     dword ptr [rax+10h], 0
0x1400093c4  lea     rcx, [rax-28h]
0x1400093c8  jnz     short loc_1400093E8
0x1400093ca  mov     dword ptr [rcx+20h], 1
0x1400093d1  mov     rdx, [r15]
0x1400093d4  cmp     [rdx+8], r15
0x1400093d8  jnz     short loc_1400093FD
0x1400093da  mov     [rcx], rdx
0x1400093dd  mov     [rcx+8], r15
0x1400093e1  mov     [rdx+8], rcx
0x1400093e5  mov     [r15], rcx
0x1400093e8  mov     rax, [rax]
0x1400093eb  cmp     rax, rsi
0x1400093ee  jnz     short loc_1400093C0
0x1400093f0  add     rsp, 20h
0x1400093f4  pop     r15
0x1400093f6  pop     r14
0x1400093f8  pop     rdi
0x1400093f9  pop     rsi
0x1400093fa  pop     rbx
0x1400093fb  retn
0x1400093fd  mov     ecx, 3
0x140009402  int     29h; Win8: RtlFailFast(ecx)
```
