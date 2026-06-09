# AllocateAndAttachRootCause(ulong *,tagHELPER_ATTRIBUTE * *,_GUID)

- ea: `0x18001795c`
- end: `0x180017abc`
- name: `?AllocateAndAttachRootCause@@YAJPEAKPEAPEAUtagHELPER_ATTRIBUTE@@U_GUID@@@Z`
- size: `352`
- prototype: `__int64 __fastcall(unsigned int *, LPVOID *, struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d650`

## callees

- `0x180006b04`
- `0x18000f2d4`
- `0x18001795c`
- `0x18001a596`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017a7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017a84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017a7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017a84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800179c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017a29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800179c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017a29`

## pseudocode

```c
__int64 __fastcall AllocateAndAttachRootCause(unsigned int *a1, LPVOID *a2, struct _GUID *a3)
{
  __int64 v6; // rbx
  struct tagHELPER_ATTRIBUTE *v7; // rax
  _QWORD *v9; // r14
  int v10; // ebx
  unsigned __int64 v11; // rbx
  unsigned __int16 *v12; // rax
  __int128 v13; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int64 v14; // [rsp+50h] [rbp+8h] BYREF

  if ( a1 && a2 && !*a2 && !*a1 )
  {
    v13 = 0;
    if ( memcmp_0(a3, &v13, 0x10u) )
    {
      v6 = 144;
      v7 = (struct tagHELPER_ATTRIBUTE *)CoTaskMemAlloc(0x90u);
      *a2 = v7;
      if ( !v7 )
        return 2147942414LL;
      do
      {
        LOBYTE(v7->pwszName) = 0;
        v7 = (struct tagHELPER_ATTRIBUTE *)((char *)v7 + 1);
        --v6;
      }
      while ( v6 );
      *((_DWORD *)*a2 + 2) = 11;
      v9 = *a2;
      if ( *a2 )
      {
        v14 = 0;
        v10 = StringCchLengthW(L"rootcauseid", 0x103u, &v14);
        if ( v10 < 0 )
          goto LABEL_16;
        v11 = v14;
        v12 = (unsigned __int16 *)CoTaskMemAlloc(2 * v14 + 2);
        *v9 = v12;
        if ( !v12 )
        {
          v10 = -2147024882;
          goto LABEL_16;
        }
        v10 = StringCchCopyW(v12, v11 + 1, L"rootcauseid");
        if ( v10 >= 0 )
        {
          *((struct _GUID *)*a2 + 1) = *a3;
          *a1 = 1;
          return (unsigned int)v10;
        }
      }
      else
      {
        v10 = -2147024809;
      }
LABEL_16:
      if ( *a2 )
      {
        CoTaskMemFree(*(LPVOID *)*a2);
        CoTaskMemFree(*a2);
        *a2 = 0;
        *a1 = 0;
      }
      return (unsigned int)v10;
    }
    v10 = 0;
    *a2 = 0;
    *a1 = 0;
    return (unsigned int)v10;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001795c  mov     rax, rsp
0x18001795f  mov     [rax+10h], rbx
0x180017963  mov     [rax+18h], rbp
0x180017967  push    rsi
0x180017968  push    rdi
0x180017969  push    r14
0x18001796b  sub     rsp, 30h
0x18001796f  mov     rbp, r8
0x180017972  mov     rdi, rdx
0x180017975  mov     rsi, rcx
0x180017978  test    rcx, rcx
0x18001797b  jz      loc_180017AA4
0x180017981  test    rdx, rdx
0x180017984  jz      loc_180017AA4
0x18001798a  cmp     qword ptr [rdx], 0
0x18001798e  jnz     loc_180017AA4
0x180017994  cmp     dword ptr [rcx], 0
0x180017997  jnz     loc_180017AA4
0x18001799d  xorps   xmm0, xmm0
0x1800179a0  lea     rdx, [rax-28h]; Buf2
0x1800179a4  mov     r8d, 10h; Size
0x1800179aa  mov     rcx, rbp; Buf1
0x1800179ad  movups  xmmword ptr [rax-28h], xmm0
0x1800179b1  call    memcmp_0
0x1800179b6  test    eax, eax
0x1800179b8  jz      loc_180017A99
0x1800179be  mov     ebx, 90h
0x1800179c3  mov     ecx, ebx; cb
0x1800179c5  call    cs:__imp_CoTaskMemAlloc
0x1800179cb  mov     [rdi], rax
0x1800179ce  test    rax, rax
0x1800179d1  jnz     short loc_1800179DD
0x1800179d3  mov     eax, 8007000Eh
0x1800179d8  jmp     loc_180017AA9
0x1800179dd  mov     byte ptr [rax], 0
0x1800179e0  inc     rax
0x1800179e3  sub     rbx, 1
0x1800179e7  jnz     short loc_1800179DD
0x1800179e9  mov     rax, [rdi]
0x1800179ec  mov     dword ptr [rax+8], 0Bh
0x1800179f3  mov     r14, [rdi]
0x1800179f6  test    r14, r14
0x1800179f9  jz      short loc_180017A6B
0x1800179fb  lea     r8, [rsp+48h+arg_0]; unsigned __int64 *
0x180017a00  mov     [rsp+48h+arg_0], rbx
0x180017a05  mov     edx, 103h; unsigned __int64
0x180017a0a  lea     rcx, aRootcauseid; "rootcauseid"
0x180017a11  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180017a16  mov     ebx, eax
0x180017a18  test    eax, eax
0x180017a1a  js      short loc_180017A70
0x180017a1c  mov     rbx, [rsp+48h+arg_0]
0x180017a21  lea     rcx, ds:2[rbx*2]; cb
0x180017a29  call    cs:__imp_CoTaskMemAlloc
0x180017a2f  mov     [r14], rax
0x180017a32  test    rax, rax
0x180017a35  jnz     short loc_180017A3E
0x180017a37  mov     ebx, 8007000Eh
0x180017a3c  jmp     short loc_180017A70
0x180017a3e  lea     rdx, [rbx+1]; unsigned __int64
0x180017a42  mov     rcx, rax; unsigned __int16 *
0x180017a45  lea     r8, aRootcauseid; "rootcauseid"
0x180017a4c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017a51  mov     ebx, eax
0x180017a53  test    eax, eax
0x180017a55  js      short loc_180017A70
0x180017a57  mov     rax, [rdi]
0x180017a5a  movaps  xmm0, xmmword ptr [rbp+0]
0x180017a5e  movdqu  xmmword ptr [rax+10h], xmm0
0x180017a63  mov     dword ptr [rsi], 1
0x180017a69  jmp     short loc_180017AA0
0x180017a6b  mov     ebx, 80070057h
0x180017a70  mov     rcx, [rdi]
0x180017a73  test    rcx, rcx
0x180017a76  jz      short loc_180017AA0
0x180017a78  mov     rcx, [rcx]; pv
0x180017a7b  call    cs:__imp_CoTaskMemFree
0x180017a81  mov     rcx, [rdi]; pv
0x180017a84  call    cs:__imp_CoTaskMemFree
0x180017a8a  mov     qword ptr [rdi], 0
0x180017a91  mov     dword ptr [rsi], 0
0x180017a97  jmp     short loc_180017AA0
0x180017a99  xor     ebx, ebx
0x180017a9b  mov     [rdi], rbx
0x180017a9e  mov     [rsi], ebx
0x180017aa0  mov     eax, ebx
0x180017aa2  jmp     short loc_180017AA9
0x180017aa4  mov     eax, 80070057h
0x180017aa9  mov     rbx, [rsp+48h+arg_8]
0x180017aae  mov     rbp, [rsp+48h+arg_10]
0x180017ab3  add     rsp, 30h
0x180017ab7  pop     r14
0x180017ab9  pop     rdi
0x180017aba  pop     rsi
0x180017abb  retn
```
