# WSTAllocateWstMessage(uchar * *,ulong *,_WST_MESSAGE * *)

- ea: `0x18000bb08`
- end: `0x18000bbc6`
- name: `?WSTAllocateWstMessage@@YAJPEAPEAEPEAKPEAPEAU_WST_MESSAGE@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(unsigned __int8 **, unsigned int *, struct _WST_MESSAGE **)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800070d0`
- `0x180008e60`
- `0x18000bf1c`
- `0x180019eec`

## callees

- `0x18000bb08`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall WSTAllocateWstMessage(unsigned __int8 **a1, unsigned int *a2, struct _WST_MESSAGE **a3)
{
  __int64 v6; // rax
  unsigned int v7; // ecx
  __int64 v8; // rdx
  __int64 v10; // rax

  if ( *((_DWORD *)WSTGlobalBaseSSP + 52) == 1 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)WSTGlobalBaseSSP + 30) + 384LL))(40);
    v7 = 0;
    v8 = v6;
    if ( v6 )
      goto LABEL_3;
    return (unsigned int)-1073741670;
  }
  v10 = (**((__int64 (__fastcall ***)(__int64))WSTGlobalBaseSSP + 31))(40);
  v7 = 0;
  v8 = v10;
  if ( !v10 )
    return (unsigned int)-1073741670;
  *(_QWORD *)(v10 + 24) = 0;
  *(_QWORD *)(v10 + 32) = 0;
LABEL_3:
  *(_QWORD *)(v8 + 16) = 0x4547534D4F545357LL;
  *(_QWORD *)(v8 + 8) = v8;
  *(_QWORD *)v8 = v8;
  if ( a1 && *a1 )
  {
    *(_QWORD *)(v8 + 24) = *a1;
    *a1 = 0;
  }
  *(_DWORD *)(v8 + 32) = *a2;
  *a2 = 0;
  *a3 = (struct _WST_MESSAGE *)v8;
  return v7;
}

```

## disassembly

```asm
0x18000bb08  mov     [rsp+arg_0], rbx
0x18000bb0d  mov     [rsp+arg_8], rsi
0x18000bb12  push    rdi
0x18000bb13  sub     rsp, 20h
0x18000bb17  mov     rax, cs:?WSTGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * WSTGlobalBaseSSP
0x18000bb1e  mov     rsi, r8
0x18000bb21  mov     rdi, rdx
0x18000bb24  mov     rbx, rcx
0x18000bb27  cmp     dword ptr [rax+0D0h], 1
0x18000bb2e  jnz     short loc_18000BB9E
0x18000bb30  mov     rax, [rax+0F0h]
0x18000bb37  mov     ecx, 28h ; '('
0x18000bb3c  mov     rax, [rax+180h]
0x18000bb43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb48  xor     ecx, ecx
0x18000bb4a  mov     rdx, rax
0x18000bb4d  test    rax, rax
0x18000bb50  jz      short loc_18000BB97
0x18000bb52  mov     rax, 4547534D4F545357h
0x18000bb5c  mov     [rdx+10h], rax
0x18000bb60  mov     [rdx+8], rdx
0x18000bb64  mov     [rdx], rdx
0x18000bb67  test    rbx, rbx
0x18000bb6a  jz      short loc_18000BB7B
0x18000bb6c  mov     rax, [rbx]
0x18000bb6f  test    rax, rax
0x18000bb72  jz      short loc_18000BB7B
0x18000bb74  mov     [rdx+18h], rax
0x18000bb78  mov     [rbx], rcx
0x18000bb7b  mov     eax, [rdi]
0x18000bb7d  mov     [rdx+20h], eax
0x18000bb80  mov     [rdi], ecx
0x18000bb82  mov     [rsi], rdx
0x18000bb85  mov     rbx, [rsp+28h+arg_0]
0x18000bb8a  mov     eax, ecx
0x18000bb8c  mov     rsi, [rsp+28h+arg_8]
0x18000bb91  add     rsp, 20h
0x18000bb95  pop     rdi
0x18000bb96  retn
0x18000bb97  mov     ecx, 0C000009Ah
0x18000bb9c  jmp     short loc_18000BB85
0x18000bb9e  mov     rax, [rax+0F8h]
0x18000bba5  mov     ecx, 28h ; '('
0x18000bbaa  mov     rax, [rax]
0x18000bbad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbb2  xor     ecx, ecx
0x18000bbb4  mov     rdx, rax
0x18000bbb7  test    rax, rax
0x18000bbba  jz      short loc_18000BB97
0x18000bbbc  mov     [rax+18h], rcx
0x18000bbc0  mov     [rax+20h], rcx
0x18000bbc4  jmp     short loc_18000BB52
```
