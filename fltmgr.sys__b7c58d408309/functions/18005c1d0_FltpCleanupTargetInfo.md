# FltpCleanupTargetInfo

- ea: `0x18005c1d0`
- end: `0x18005c3aa`
- name: `FltpCleanupTargetInfo`
- size: `474`
- prototype: `void __fastcall(void *, void *, ULONG_PTR)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18001bf00`
- `0x18005aa30`
- `0x18005d2b0`

## callees

- `0x180010400`
- `0x1800148b0`
- `0x180014cf0`
- `0x18002289c`
- `0x18005c1d0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18005c2c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005c2c2`
- `ntoskrnl!KeBugCheckEx` at `0x18005c303`
- `ntoskrnl!KeBugCheckEx` at `0x18005c303`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18005c29a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18005c38f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18005c29a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18005c38f`

## pseudocode

```c
void __fastcall FltpCleanupTargetInfo(void *a1, void *a2, ULONG_PTR a3)
{
  int v5; // ecx
  __int64 v6; // rax
  unsigned __int64 v7; // rax
  void *v8; // rdx
  unsigned __int64 v9; // rax
  ULONG v10; // edx
  unsigned int v11; // [rsp+28h] [rbp-20h]

  if ( a1 )
    FltObjectDereference(a1);
  if ( a2 )
    FltObjectDereference(a2);
  if ( a3 )
  {
    if ( (byte_1800404C3 & 8) != 0 )
      McTemplateU0sp_EtwWriteTransfer((__int64)a1, (__int64)NameCacheSup_c6404, "FltReleaseFileNameInformation", a3);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a3 + 120), 0xFFFFFFFF) <= 1 )
    {
      if ( (*(_DWORD *)(a3 - 8) & 0x1E000) != 0 )
        KeBugCheckEx(0xF5u, 0x68u, a3 - 80, a3, 0);
      if ( (byte_1800404C3 & 8) != 0 )
        McTemplateU0s_EtwWriteTransfer((__int64)a1, (__int64)NameCacheSup_c6433, "FltReleaseFileNameInformation");
      if ( (byte_1800404C3 & 2) != 0 )
      {
        v11 = *(unsigned __int16 *)(a3 + 8) >> 1;
        McTemplateU0spdw_EtwWriteTransfer(
          (unsigned __int16)*(_DWORD *)(a3 - 8),
          v11,
          a3,
          a3 - 80,
          (unsigned __int16)*(_DWORD *)(a3 - 8),
          v11,
          *(_QWORD *)(a3 + 16));
      }
      v5 = *(_DWORD *)(a3 - 8);
      if ( (v5 & 0x1000) != 0 )
      {
        v6 = *(unsigned __int16 *)(a3 - 78);
        if ( (unsigned __int16)v6 <= 0x150u )
          LOWORD(v7) = 0;
        else
          v7 = (unsigned __int64)(v6 - 273) >> 6;
        v8 = (void *)(a3 - 80);
        v9 = (unsigned __int64)(unsigned __int16)v7 << 7;
        if ( (v5 & 0x800) != 0 )
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)qword_18003F840 + v9), v8);
        else
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)qword_18003F4C0 + v9), v8);
      }
      else
      {
        if ( (v5 & 0x800) != 0 )
          v10 = 946752838;
        else
          v10 = 846089542;
        ExFreePoolWithTag((PVOID)(a3 - 80), v10);
      }
    }
    if ( (byte_1800404C3 & 8) != 0 )
      McTemplateU0s_EtwWriteTransfer((__int64)a1, (__int64)NameCacheSup_c6442, "FltReleaseFileNameInformation");
  }
}

```

## disassembly

```asm
0x18005c1d0  mov     [rsp+arg_0], rbx
0x18005c1d5  push    rdi
0x18005c1d6  sub     rsp, 40h
0x18005c1da  mov     rdi, r8
0x18005c1dd  mov     rbx, rdx
0x18005c1e0  test    rcx, rcx
0x18005c1e3  jnz     loc_18005C328
0x18005c1e9  test    rbx, rbx
0x18005c1ec  jnz     loc_18005C332
0x18005c1f2  test    rdi, rdi
0x18005c1f5  jz      short loc_18005C220
0x18005c1f7  test    cs:byte_1800404C3, 8
0x18005c1fe  jnz     loc_18005C33F
0x18005c204  mov     eax, 0FFFFFFFFh
0x18005c209  lock xadd [rdi+78h], eax
0x18005c20e  sub     eax, 1
0x18005c211  jle     short loc_18005C22C
0x18005c213  test    cs:byte_1800404C3, 8
0x18005c21a  jnz     loc_18005C2D3
0x18005c220  mov     rbx, [rsp+48h+arg_0]
0x18005c225  add     rsp, 40h
0x18005c229  pop     rdi
0x18005c22a  retn
0x18005c22c  test    dword ptr [rdi-8], 1E000h
0x18005c233  jnz     loc_18005C2EB
0x18005c239  test    cs:byte_1800404C3, 8
0x18005c240  jnz     loc_18005C310
0x18005c246  test    cs:byte_1800404C3, 2
0x18005c24d  jnz     loc_18005C35A
0x18005c253  mov     ecx, [rdi-8]
0x18005c256  bt      ecx, 0Ch
0x18005c25a  jnb     short loc_18005C2AF
0x18005c25c  movzx   eax, word ptr [rdi-4Eh]
0x18005c260  mov     edx, 150h
0x18005c265  cmp     ax, dx
0x18005c268  jbe     short loc_18005C2AB
0x18005c26a  sub     rax, 111h
0x18005c270  shr     rax, 6
0x18005c274  movzx   eax, ax
0x18005c277  lea     rdx, [rdi-50h]; Entry
0x18005c27b  shl     rax, 7
0x18005c27f  bt      ecx, 0Bh
0x18005c283  lea     rcx, FltGlobals
0x18005c28a  jb      loc_18005C385
0x18005c290  add     rcx, 0D80h
0x18005c297  add     rcx, rax; Lookaside
0x18005c29a  call    cs:__imp_ExFreeToPagedLookasideList
0x18005c2a1  nop     dword ptr [rax+rax+00h]
0x18005c2a6  jmp     loc_18005C213
0x18005c2ab  xor     eax, eax
0x18005c2ad  jmp     short loc_18005C274
0x18005c2af  bt      ecx, 0Bh
0x18005c2b3  lea     rcx, [rdi-50h]; P
0x18005c2b7  jb      loc_18005C3A0
0x18005c2bd  mov     edx, 326E4D46h; Tag
0x18005c2c2  call    cs:__imp_ExFreePoolWithTag
0x18005c2c9  nop     dword ptr [rax+rax+00h]
0x18005c2ce  jmp     loc_18005C213
0x18005c2d3  lea     r8, aFltreleasefile; "FltReleaseFileNameInformation"
0x18005c2da  lea     rdx, NameCacheSup_c6442
0x18005c2e1  call    McTemplateU0s_EtwWriteTransfer
0x18005c2e6  jmp     loc_18005C220
0x18005c2eb  xor     eax, eax
0x18005c2ed  lea     r8, [rdi-50h]; BugCheckParameter2
0x18005c2f1  mov     r9, rdi; BugCheckParameter3
0x18005c2f4  mov     [rsp+48h+BugCheckParameter4], rax; BugCheckParameter4
0x18005c2f9  mov     edx, 68h ; 'h'; BugCheckParameter1
0x18005c2fe  mov     ecx, 0F5h; BugCheckCode
0x18005c303  call    cs:__imp_KeBugCheckEx
0x18005c310  lea     r8, aFltreleasefile; "FltReleaseFileNameInformation"
0x18005c317  lea     rdx, NameCacheSup_c6433
0x18005c31e  call    McTemplateU0s_EtwWriteTransfer
0x18005c323  jmp     loc_18005C246
0x18005c328  call    FltObjectDereference
0x18005c32d  jmp     loc_18005C1E9
0x18005c332  mov     rcx, rbx; FltObject
0x18005c335  call    FltObjectDereference
0x18005c33a  jmp     loc_18005C1F2
0x18005c33f  mov     r9, rdi
0x18005c342  lea     r8, aFltreleasefile; "FltReleaseFileNameInformation"
0x18005c349  lea     rdx, NameCacheSup_c6404
0x18005c350  call    McTemplateU0sp_EtwWriteTransfer
0x18005c355  jmp     loc_18005C204
0x18005c35a  mov     eax, [rdi-8]
0x18005c35d  lea     r9, [rdi-50h]
0x18005c361  movzx   edx, word ptr [rdi+8]
0x18005c365  movzx   ecx, ax
0x18005c368  mov     rax, [rdi+10h]
0x18005c36c  mov     [rsp+48h+var_18], rax
0x18005c371  shr     edx, 1
0x18005c373  mov     [rsp+48h+var_20], edx
0x18005c377  mov     dword ptr [rsp+48h+BugCheckParameter4], ecx
0x18005c37b  call    McTemplateU0spdw_EtwWriteTransfer
0x18005c380  jmp     loc_18005C253
0x18005c385  add     rcx, 1100h
0x18005c38c  add     rcx, rax; Lookaside
0x18005c38f  call    cs:__imp_ExFreeToPagedLookasideList
0x18005c396  nop     dword ptr [rax+rax+00h]
0x18005c39b  jmp     loc_18005C213
0x18005c3a0  mov     edx, 386E4D46h
0x18005c3a5  jmp     loc_18005C2C2
```
