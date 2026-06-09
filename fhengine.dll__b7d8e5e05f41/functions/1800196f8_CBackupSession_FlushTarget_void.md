# CBackupSession::FlushTarget(void)

- ea: `0x1800196f8`
- end: `0x1800198bb`
- name: `?FlushTarget@CBackupSession@@AEAAJXZ`
- size: `451`
- prototype: `__int64 __fastcall(CBackupSession *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180021240`

## callees

- `0x180002c24`
- `0x1800062d0`
- `0x1800077f0`
- `0x180007818`
- `0x1800091a4`
- `0x180009404`
- `0x180009920`
- `0x18000a1ec`
- `0x18000bca8`
- `0x18000edc4`
- `0x1800196f8`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x1800197ae`
- `ADVAPI32!SetThreadToken` at `0x1800197ae`
- `KERNEL32!GetLastError` at `0x1800197b8`
- `KERNEL32!GetLastError` at `0x1800197b8`

## pseudocode

```c
__int64 __fastcall CBackupSession::FlushTarget(CBackupSession *this)
{
  char *v2; // rdx
  volatile signed __int32 *v3; // rcx
  int *v4; // rbx
  volatile signed __int32 *v5; // rdi
  __int64 v6; // rcx
  unsigned __int16 v7; // ax
  signed int LastError; // eax
  unsigned int v9; // ebx
  PVOID *v10; // r10
  int v11; // eax
  int v13[6]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v14; // [rsp+40h] [rbp+8h] BYREF
  LPCWSTR v15; // [rsp+48h] [rbp+10h] BYREF
  _DWORD *v16; // [rsp+50h] [rbp+18h]

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v15);
  v16 = (_DWORD *)((char *)this + 116);
  if ( *((_DWORD *)this + 29) == 4 )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v2 = (char *)*ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                      &v14,
                      (_QWORD *)this + 11);
      v3 = (volatile signed __int32 *)(v2 - 24);
      v4 = (int *)(v15 - 12);
      if ( v2 - 24 != (char *)(v15 - 12) )
      {
        if ( v4[4] >= 0 && *(_QWORD *)v3 == *(_QWORD *)v4 )
        {
          v5 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v3);
          ATL::CStringData::Release((ATL::CStringData *)v4);
          v15 = (LPCWSTR)(v5 + 6);
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString((__int64 *)&v15, v2, *((_DWORD *)v2 - 4));
        }
      }
      ATL::CStringData::Release((ATL::CStringData *)(v14 - 24));
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)v13) )
      {
        LODWORD(v14) = v13[0];
        if ( v13[0] < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              71,
              &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
              (unsigned int)v13[0]);
          v9 = v14;
          v10 = (PVOID *)WPP_GLOBAL_Control;
          __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18001980A);
          goto LABEL_15;
        }
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_180019822);
      }
    }
  }
  else
  {
    v7 = ATL::CSimpleStringT<unsigned short,0>::operator[]((char *)this + 72, 0);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      (__int64)&v15,
      (__int64)L"\\\\?\\%c:",
      v7);
    if ( !SetThreadToken(0, 0) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, v9);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
LABEL_15:
      if ( (v9 & 0x80000000) == 0 )
        goto LABEL_26;
      goto LABEL_21;
    }
  }
  v11 = CSessionBaseRW::FlushFile(v6, &v15);
  v9 = v11;
  if ( v11 >= 0 )
    goto LABEL_26;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      72,
      &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
      (unsigned int)v11);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_21:
  if ( ((*v16 - 2) & 0xFFFFFFFD) == 0 )
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
      WPP_SF_(v10[2], 73, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
    v9 = 0;
  }
LABEL_26:
  ATL::CStringData::Release((ATL::CStringData *)(v15 - 12));
  return v9;
}

```

## disassembly

```asm
0x1800196f8  mov     [rsp+arg_18], rbx
0x1800196fd  push    rdi
0x1800196fe  sub     rsp, 30h
0x180019702  mov     rbx, rcx
0x180019705  lea     rcx, [rsp+38h+arg_8]
0x18001970a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001970f  nop
0x180019710  lea     rax, [rbx+74h]
0x180019714  mov     [rsp+38h+arg_10], rax
0x180019719  cmp     dword ptr [rax], 4
0x18001971c  jnz     short loc_18001978A
0x18001971e  lea     rdx, [rbx+58h]
0x180019722  lea     rcx, [rsp+38h+arg_0]
0x180019727  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001972c  nop
0x18001972d  mov     rdx, [rax]
0x180019730  lea     rcx, [rdx-18h]
0x180019734  mov     rbx, [rsp+38h+arg_8]
0x180019739  add     rbx, 0FFFFFFFFFFFFFFE8h
0x18001973d  cmp     rcx, rbx
0x180019740  jz      short loc_18001977A
0x180019742  cmp     dword ptr [rbx+10h], 0
0x180019746  jl      short loc_18001976B
0x180019748  mov     rax, [rbx]
0x18001974b  cmp     [rcx], rax
0x18001974e  jnz     short loc_18001976B
0x180019750  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180019755  mov     rdi, rax
0x180019758  mov     rcx, rbx; this
0x18001975b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180019760  lea     rax, [rdi+18h]
0x180019764  mov     [rsp+38h+arg_8], rax
0x180019769  jmp     short loc_18001977A
0x18001976b  mov     r8d, [rdx-10h]
0x18001976f  lea     rcx, [rsp+38h+arg_8]
0x180019774  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180019779  nop
0x18001977a  mov     rcx, [rsp+38h+arg_0]
0x18001977f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180019783  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180019788  jmp     short loc_180019808
0x18001978a  lea     rcx, [rbx+48h]
0x18001978e  xor     edx, edx
0x180019790  call    ??A?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::operator[](int)
0x180019795  movzx   r8d, ax
0x180019799  lea     rdx, aC; "\\\\?\\%c:"
0x1800197a0  lea     rcx, [rsp+38h+arg_8]
0x1800197a5  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800197aa  xor     edx, edx; Token
0x1800197ac  xor     ecx, ecx; Thread
0x1800197ae  call    cs:__imp_SetThreadToken
0x1800197b4  test    eax, eax
0x1800197b6  jnz     short loc_180019808
0x1800197b8  call    cs:__imp_GetLastError
0x1800197be  mov     ebx, eax
0x1800197c0  test    eax, eax
0x1800197c2  jle     short loc_1800197CD
0x1800197c4  movzx   ebx, ax
0x1800197c7  or      ebx, 80070000h
0x1800197cd  lea     rdi, WPP_GLOBAL_Control
0x1800197d4  mov     r10, cs:WPP_GLOBAL_Control
0x1800197db  cmp     r10, rdi
0x1800197de  jz      short loc_180019806
0x1800197e0  test    byte ptr [r10+1Ch], 1
0x1800197e5  jz      short loc_180019806
0x1800197e7  mov     edx, 46h ; 'F'
0x1800197ec  mov     r9d, ebx
0x1800197ef  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x1800197f6  mov     rcx, [r10+10h]
0x1800197fa  call    WPP_SF_d
0x1800197ff  mov     r10, cs:WPP_GLOBAL_Control
0x180019806  jmp     short loc_18001981C
0x180019808  jmp     short loc_180019822
0x18001980a  lea     rdi, WPP_GLOBAL_Control
0x180019811  mov     ebx, dword ptr [rsp+38h+arg_0]
0x180019815  mov     r10, cs:WPP_GLOBAL_Control
0x18001981c  test    ebx, ebx
0x18001981e  js      short loc_18001986B
0x180019820  jmp     short loc_1800198A0
0x180019822  lea     rdx, [rsp+38h+arg_8]
0x180019827  call    ?FlushFile@CSessionBaseRW@@IEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CSessionBaseRW::FlushFile(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001982c  mov     ebx, eax
0x18001982e  test    eax, eax
0x180019830  jns     short loc_1800198A0
0x180019832  lea     rdi, WPP_GLOBAL_Control
0x180019839  mov     r10, cs:WPP_GLOBAL_Control
0x180019840  cmp     r10, rdi
0x180019843  jz      short loc_18001986B
0x180019845  test    byte ptr [r10+1Ch], 1
0x18001984a  jz      short loc_18001986B
0x18001984c  mov     edx, 48h ; 'H'
0x180019851  mov     r9d, eax
0x180019854  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001985b  mov     rcx, [r10+10h]
0x18001985f  call    WPP_SF_d
0x180019864  mov     r10, cs:WPP_GLOBAL_Control
0x18001986b  mov     rax, [rsp+38h+arg_10]
0x180019870  mov     ecx, [rax]
0x180019872  sub     ecx, 2
0x180019875  test    ecx, 0FFFFFFFDh
0x18001987b  jnz     short loc_1800198A0
0x18001987d  cmp     r10, rdi
0x180019880  jz      short loc_18001989E
0x180019882  test    byte ptr [r10+1Ch], 8
0x180019887  jz      short loc_18001989E
0x180019889  mov     edx, 49h ; 'I'
0x18001988e  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180019895  mov     rcx, [r10+10h]
0x180019899  call    WPP_SF_
0x18001989e  xor     ebx, ebx
0x1800198a0  mov     rcx, [rsp+38h+arg_8]
0x1800198a5  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800198a9  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800198ae  mov     eax, ebx
0x1800198b0  mov     rbx, [rsp+38h+arg_18]
0x1800198b5  add     rsp, 30h
0x1800198b9  pop     rdi
0x1800198ba  retn
```
