# PrjfOpenParentPlaceHolder

- ea: `0x14000752c`
- end: `0x14000768b`
- name: `PrjfOpenParentPlaceHolder`
- size: `351`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400081f0`
- `0x140039de8`

## callees

- `0x14000752c`
- `0x14000d754`
- `0x14003c4b8`

## import_xrefs

- `FLTMGR!FltParseFileNameInformation` at `0x140007584`
- `FLTMGR!FltParseFileNameInformation` at `0x140007584`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000766e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000766e`
- `FLTMGR!FltGetFileNameInformation` at `0x140007569`
- `FLTMGR!FltGetFileNameInformation` at `0x140007569`

## pseudocode

```c
__int64 __fastcall PrjfOpenParentPlaceHolder(
        struct _FLT_CALLBACK_DATA *a1,
        struct _FLT_INSTANCE *a2,
        void **a3,
        PVOID *a4,
        _BYTE *a5)
{
  int v8; // ebx
  __int64 v9; // r8
  struct _FLT_FILE_NAME_INFORMATION *v10; // rax
  int v11; // edx
  int v12; // r8d
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+60h] [rbp-48h] BYREF
  struct _UNICODE_STRING v15[4]; // [rsp+68h] [rbp-40h] BYREF

  FileNameInformation = 0;
  *a5 = 0;
  v15[0] = 0;
  v8 = FltGetFileNameInformation(a1, 0x101u, &FileNameInformation);
  if ( v8 >= 0 )
  {
    v8 = FltParseFileNameInformation(FileNameInformation);
    if ( v8 >= 0 )
    {
      v10 = FileNameInformation;
      if ( FileNameInformation->ParentDir.Length == 2 )
        goto LABEL_9;
      v15[0] = FileNameInformation->Name;
      v15[0].Length = -2 - FileNameInformation->FinalComponent.Length + _mm_cvtsi128_si32((__m128i)v15[0]);
      v8 = PrjfOpenPlaceHolder(a2, v15, v9, a3, a4, a5);
      if ( v8 < 0
        && ((BYTE1(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
      {
        LOBYTE(v11) = BYTE1(xmmword_14001A3D0) & 4;
        LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          522,
          v11,
          v12,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          10,
          60,
          (__int64)&WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          190,
          v8,
          (__int64)v15);
      }
    }
  }
  v10 = FileNameInformation;
LABEL_9:
  if ( v10 )
    FltReleaseFileNameInformation(v10);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000752c  push    rbx
0x14000752e  push    rbp
0x14000752f  push    rsi
0x140007530  push    rdi
0x140007531  push    r14
0x140007533  sub     rsp, 80h
0x14000753a  mov     rdi, [rsp+0A8h+arg_20]
0x140007542  mov     rbp, r8
0x140007545  mov     r14, rdx
0x140007548  mov     [rsp+0A8h+FileNameInformation], 0
0x140007551  xorps   xmm0, xmm0
0x140007554  lea     r8, [rsp+0A8h+FileNameInformation]; FileNameInformation
0x140007559  mov     edx, 101h; NameOptions
0x14000755e  mov     rsi, r9
0x140007561  mov     byte ptr [rdi], 0
0x140007564  movups  [rsp+0A8h+var_40], xmm0
0x140007569  call    cs:__imp_FltGetFileNameInformation
0x140007570  nop     dword ptr [rax+rax+00h]
0x140007575  mov     ebx, eax
0x140007577  test    eax, eax
0x140007579  js      loc_140007661
0x14000757f  mov     rcx, [rsp+0A8h+FileNameInformation]; FileNameInformation
0x140007584  call    cs:__imp_FltParseFileNameInformation
0x14000758b  nop     dword ptr [rax+rax+00h]
0x140007590  mov     ebx, eax
0x140007592  test    eax, eax
0x140007594  js      loc_140007661
0x14000759a  mov     rax, [rsp+0A8h+FileNameInformation]
0x14000759f  cmp     word ptr [rax+68h], 2
0x1400075a4  jz      loc_140007666
0x1400075aa  movups  xmm0, xmmword ptr [rax+8]
0x1400075ae  mov     ecx, 0FFFEh
0x1400075b3  mov     [rsp+0A8h+var_80], rdi
0x1400075b8  mov     r9, rbp
0x1400075bb  mov     [rsp+0A8h+var_88], rsi
0x1400075c0  movups  [rsp+0A8h+var_40], xmm0
0x1400075c5  sub     cx, [rax+58h]
0x1400075c9  lea     rdx, [rsp+0A8h+var_40]
0x1400075ce  movd    eax, xmm0
0x1400075d2  add     ax, cx
0x1400075d5  mov     rcx, r14
0x1400075d8  mov     word ptr [rsp+0A8h+var_40], ax
0x1400075dd  call    PrjfOpenPlaceHolder
0x1400075e2  mov     ebx, eax
0x1400075e4  test    eax, eax
0x1400075e6  jns     short loc_140007661
0x1400075e8  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400075ee  lea     rax, WPP_RECORDER_INITIALIZED
0x1400075f5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400075fc  setnz   r8b
0x140007600  and     dl, 4
0x140007603  jnz     short loc_14000760A
0x140007605  test    r8b, r8b
0x140007608  jz      short loc_140007661
0x14000760a  mov     r9, cs:WPP_GLOBAL_Control
0x140007611  lea     rax, [rsp+0A8h+var_40]
0x140007616  mov     [rsp+0A8h+var_50], rax
0x14000761b  mov     ecx, 20Ah
0x140007620  mov     [rsp+0A8h+var_58], ebx
0x140007624  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000762b  mov     [rsp+0A8h+var_60], 0ABEh
0x140007633  mov     r9, [r9+40h]
0x140007637  mov     [rsp+0A8h+var_68], rax
0x14000763c  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140007643  mov     [rsp+0A8h+var_70], rax
0x140007648  mov     [rsp+0A8h+var_78], 3Ch ; '<'
0x14000764f  mov     dword ptr [rsp+0A8h+var_80], 0Ah
0x140007657  mov     byte ptr [rsp+0A8h+var_88], 2
0x14000765c  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140007661  mov     rax, [rsp+0A8h+FileNameInformation]
0x140007666  test    rax, rax
0x140007669  jz      short loc_14000767A
0x14000766b  mov     rcx, rax; FileNameInformation
0x14000766e  call    cs:__imp_FltReleaseFileNameInformation
0x140007675  nop     dword ptr [rax+rax+00h]
0x14000767a  mov     eax, ebx
0x14000767c  add     rsp, 80h
0x140007683  pop     r14
0x140007685  pop     rdi
0x140007686  pop     rsi
0x140007687  pop     rbp
0x140007688  pop     rbx
0x140007689  retn
```
