# AggregateWaitHandle::AddHandle(void *)

- ea: `0x18006d648`
- end: `0x18006d791`
- name: `?AddHandle@AggregateWaitHandle@@QEAAJPEAX@Z`
- size: `329`
- prototype: `__int64 __fastcall(AggregateWaitHandle *__hidden this, void *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005d190`
- `0x180085e30`
- `0x180142e7c`

## callees

- `0x18006d648`
- `0x1800e795c`
- `0x1800f2448`

## import_xrefs

- `ntdll!NtAssociateWaitCompletionPacket` at `0x18006d6df`
- `ntdll!NtAssociateWaitCompletionPacket` at `0x18006d6df`
- `ntdll!NtCreateWaitCompletionPacket` at `0x18006d69d`
- `ntdll!NtCreateWaitCompletionPacket` at `0x18006d69d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d783`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d783`

## pseudocode

```c
__int64 __fastcall AggregateWaitHandle::AddHandle(AggregateWaitHandle *this, void *a2)
{
  char *v4; // rdi
  char *i; // rax
  int v6; // esi
  char **v7; // rcx
  char *v8; // rax
  __int64 result; // rax
  _OWORD *v10; // rax
  HANDLE hObject; // [rsp+70h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 1) )
  {
    SipcFailFast(2147549183LL);
    __debugbreak();
  }
  v4 = (char *)this + 24;
  for ( i = (char *)*((_QWORD *)this + 3); i != v4; i = *(char **)i )
  {
    if ( *((void **)i + 2) == a2 )
      return 2147942487LL;
  }
  if ( !*((_QWORD *)this + 2) )
  {
    v10 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v10 )
    {
      result = 2147942414LL;
LABEL_11:
      *((_QWORD *)this + 2) = 0;
      return result;
    }
    *v10 = 0;
    v10[1] = 0;
    *((_QWORD *)this + 2) = v10;
  }
  hObject = 0;
  v6 = NtCreateWaitCompletionPacket(&hObject, 1);
  if ( v6 >= 0 )
  {
    v6 = NtAssociateWaitCompletionPacket(hObject, *(_QWORD *)this, a2, *((_QWORD *)this + 2), 0, 0, 0, 0);
    if ( v6 >= 0 )
    {
      *(_QWORD *)(*((_QWORD *)this + 2) + 16LL) = a2;
      *(_QWORD *)(*((_QWORD *)this + 2) + 24LL) = hObject;
      v7 = (char **)*((_QWORD *)v4 + 1);
      if ( *v7 != v4 )
        __fastfail(3u);
      v8 = (char *)*((_QWORD *)this + 2);
      *(_QWORD *)v8 = v4;
      *((_QWORD *)v8 + 1) = v7;
      *v7 = v8;
      ++*((_DWORD *)v4 + 4);
      *((_QWORD *)v4 + 1) = v8;
      result = 0;
      goto LABEL_11;
    }
    CloseHandle(hObject);
  }
  return v6 | 0x10000000u;
}

```

## disassembly

```asm
0x18006d648  push    rbx
0x18006d64a  push    rbp
0x18006d64b  push    rsi
0x18006d64c  push    rdi
0x18006d64d  sub     rsp, 48h
0x18006d651  cmp     qword ptr [rcx+8], 0
0x18006d656  mov     rbp, rdx
0x18006d659  mov     rbx, rcx
0x18006d65c  jz      loc_18006D759
0x18006d662  lea     rdi, [rcx+18h]
0x18006d666  mov     rax, [rdi]
0x18006d669  cmp     rax, rdi
0x18006d66c  jz      short loc_18006D67D
0x18006d66e  cmp     [rax+10h], rbp
0x18006d672  jz      loc_18006D752
0x18006d678  mov     rax, [rax]
0x18006d67b  jmp     short loc_18006D669
0x18006d67d  cmp     qword ptr [rcx+10h], 0
0x18006d682  jz      loc_18006D735
0x18006d688  xor     r8d, r8d
0x18006d68b  mov     [rsp+68h+hObject], 0
0x18006d694  lea     rcx, [rsp+68h+hObject]
0x18006d699  lea     edx, [r8+1]
0x18006d69d  call    cs:__imp_NtCreateWaitCompletionPacket
0x18006d6a3  mov     esi, eax
0x18006d6a5  test    eax, eax
0x18006d6a7  js      loc_18006D789
0x18006d6ad  mov     r9, [rbx+10h]
0x18006d6b1  mov     r8, rbp
0x18006d6b4  mov     rdx, [rbx]
0x18006d6b7  mov     rcx, [rsp+68h+hObject]
0x18006d6bc  mov     [rsp+68h+var_30], 0
0x18006d6c5  mov     [rsp+68h+var_38], 0
0x18006d6ce  mov     [rsp+68h+var_40], 0
0x18006d6d6  mov     [rsp+68h+var_48], 0
0x18006d6df  call    cs:__imp_NtAssociateWaitCompletionPacket
0x18006d6e5  mov     esi, eax
0x18006d6e7  test    eax, eax
0x18006d6e9  js      loc_18006D77E
0x18006d6ef  mov     rax, [rbx+10h]
0x18006d6f3  mov     [rax+10h], rbp
0x18006d6f7  mov     rcx, [rbx+10h]
0x18006d6fb  mov     rax, [rsp+68h+hObject]
0x18006d700  mov     [rcx+18h], rax
0x18006d704  mov     rcx, [rdi+8]
0x18006d708  cmp     [rcx], rdi
0x18006d70b  jnz     short loc_18006D777
0x18006d70d  mov     rax, [rbx+10h]
0x18006d711  mov     [rax], rdi
0x18006d714  mov     [rax+8], rcx
0x18006d718  mov     [rcx], rax
0x18006d71b  inc     dword ptr [rdi+10h]
0x18006d71e  mov     [rdi+8], rax
0x18006d722  xor     eax, eax
0x18006d724  mov     qword ptr [rbx+10h], 0
0x18006d72c  add     rsp, 48h
0x18006d730  pop     rdi
0x18006d731  pop     rsi
0x18006d732  pop     rbp
0x18006d733  pop     rbx
0x18006d734  retn
0x18006d735  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006d73c  mov     ecx, 20h ; ' '; unsigned __int64
0x18006d741  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006d746  test    rax, rax
0x18006d749  jnz     short loc_18006D764
0x18006d74b  mov     eax, 8007000Eh
0x18006d750  jmp     short loc_18006D724
0x18006d752  mov     eax, 80070057h
0x18006d757  jmp     short loc_18006D72C
0x18006d759  mov     ecx, 8000FFFFh
0x18006d75e  call    SipcFailFast
0x18006d763  int     3; Trap to Debugger
0x18006d764  xorps   xmm0, xmm0
0x18006d767  movups  xmmword ptr [rax], xmm0
0x18006d76a  movups  xmmword ptr [rax+10h], xmm0
0x18006d76e  mov     [rbx+10h], rax
0x18006d772  jmp     loc_18006D688
0x18006d777  mov     ecx, 3
0x18006d77c  int     29h; Win8: RtlFailFast(ecx)
0x18006d77e  mov     rcx, [rsp+68h+hObject]; hObject
0x18006d783  call    cs:__imp_CloseHandle
0x18006d789  bts     esi, 1Ch
0x18006d78d  mov     eax, esi
0x18006d78f  jmp     short loc_18006D72C
```
