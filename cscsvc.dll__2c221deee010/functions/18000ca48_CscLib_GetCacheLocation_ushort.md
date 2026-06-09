# CscLib_GetCacheLocation(ushort * *)

- ea: `0x18000ca48`
- end: `0x18000ce76`
- name: `?CscLib_GetCacheLocation@@YAJPEAPEAG@Z`
- size: `1070`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `3`
- callee_count: `18`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003db90`
- `0x1800616f0`
- `0x180061770`

## callees

- `0x18000a6c8`
- `0x18000b5dc`
- `0x18000ca48`
- `0x18000d640`
- `0x18000d88c`
- `0x18000d940`
- `0x18000dca0`
- `0x18001a0c0`
- `0x18001b4e0`
- `0x18001ba60`
- `0x180029ee0`
- `0x18002a478`
- `0x18002edac`
- `0x18002f078`
- `0x180036394`
- `0x180039610`
- `0x180044554`
- `0x18007f9e8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cab4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cab4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca8d`
- `KERNEL32!CompareStringW` at `0x18000cce9`
- `KERNEL32!CompareStringW` at `0x18000ce0d`
- `KERNEL32!CompareStringW` at `0x18000cce9`
- `KERNEL32!CompareStringW` at `0x18000ce0d`

## pseudocode

```c
__int64 __fastcall CscLib_GetCacheLocation(unsigned __int16 **a1)
{
  unsigned __int16 *v1; // rbx
  HANDLE ProcessHeap; // rax
  void *v4; // rdx
  int v5; // edi
  const wchar_t *v6; // rax
  WCHAR v8; // si
  WCHAR v9; // r14
  unsigned __int16 *v10; // r15
  int LocationDatabaseFsControl; // edi
  CObjectMonitor *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  int v15; // edx
  void *v16; // rdx
  int v17; // edi
  int v18; // eax
  int v19; // eax
  const unsigned __int16 *ConstBuffer; // rax
  WCHAR *lpString2; // [rsp+20h] [rbp-E0h]
  WCHAR v22; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE FileHandle; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR *v24[65]; // [rsp+40h] [rbp-C0h] BYREF
  int v25; // [rsp+248h] [rbp+148h]
  WCHAR **v26; // [rsp+250h] [rbp+150h]
  WCHAR **v27; // [rsp+258h] [rbp+158h]
  WCHAR **v28; // [rsp+260h] [rbp+160h]
  __int64 v29; // [rsp+268h] [rbp+168h]
  __int64 v30; // [rsp+270h] [rbp+170h]
  WCHAR v31[8]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR String2[12]; // [rsp+290h] [rbp+190h] BYREF

  v1 = 0;
  *a1 = 0;
  *(_QWORD *)v31 = 0;
  ProcessHeap = GetProcessHeap();
  v4 = 0;
  v5 = -2147418113;
  if ( !ProcessHeap
    || (v5 = 0, *(_QWORD *)v31 = HeapAlloc(ProcessHeap, 8u, 0x208u), (v1 = *(unsigned __int16 **)v31) != 0) )
  {
    if ( v5 < 0 )
      goto LABEL_4;
    v8 = 0;
    v9 = 520;
    *(_QWORD *)String2 = 34078720;
    v10 = v1;
    *(_QWORD *)&String2[4] = v1;
    v22 = 0;
    if ( !CscUmpLibraryState )
    {
      LocationDatabaseFsControl = -1073741436;
LABEL_13:
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v13 = 45;
        v14 = (unsigned int)LocationDatabaseFsControl;
LABEL_33:
        WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_640353d05de230bd321f309b7bf8540c_Traceguids, v14);
        goto LABEL_21;
      }
      goto LABEL_21;
    }
    FileHandle = 0;
    LocationDatabaseFsControl = CscDriverpReferenceControlHandle(&FileHandle);
    if ( LocationDatabaseFsControl >= 0 )
    {
      LocationDatabaseFsControl = CscDriverpQueryLocationDatabaseFsControl(FileHandle);
      CscDriverpDereferenceControlHandle(&FileHandle);
      v8 = v22;
      v10 = *(unsigned __int16 **)&String2[4];
      v9 = String2[1];
    }
    if ( LocationDatabaseFsControl < 0 )
    {
      if ( LocationDatabaseFsControl != -2147483643 )
        goto LABEL_13;
    }
    else if ( v9 - (unsigned __int64)String2[0] >= 2 )
    {
      v10[(unsigned __int64)String2[0] >> 1] = 0;
      goto LABEL_21;
    }
    v18 = CscUtil_HeapReAlloc(v8, v15, v1, (void **)v31, lpString2);
    v1 = *(unsigned __int16 **)v31;
    v5 = v18;
    if ( v18 < 0 )
      goto LABEL_4;
    *(_QWORD *)String2 = 0;
    String2[1] = v8;
    *(_QWORD *)&String2[4] = *(_QWORD *)v31;
    v19 = CscUmQueryDatabaseLocation(String2, &v22);
    LocationDatabaseFsControl = v19;
    if ( v19 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v13 = 44;
        v14 = (unsigned int)v19;
        goto LABEL_33;
      }
    }
LABEL_21:
    if ( LocationDatabaseFsControl )
    {
      v5 = ResultFromNtStatus(LocationDatabaseFsControl);
      goto LABEL_4;
    }
    v27 = v24;
    v29 = 520;
    v28 = v24;
    v30 = 520;
    v26 = v24;
    LOWORD(v24[0]) = 0;
    wcscpy(String2, L"\\SystemRoot");
    v25 = 34078720;
    wcscpy(v31, L"\\??\\");
    if ( CompareStringW(0x7Fu, 1u, v1, 11, String2, 11) == 2 )
    {
      FileHandle = 0;
      if ( (int)CscUtil_ExpandEnvironmentStringsAlloc(L"%SystemRoot%", (unsigned __int16 **)&FileHandle) < 0 )
        goto LABEL_39;
      v17 = CPath::Copy((CPath *)v24, (const unsigned __int16 *)FileHandle);
      if ( v17 >= 0 )
        v17 = CPath::Append((CPath *)v24, v1 + 11);
      CscUtil_HeapFree(FileHandle, v16);
    }
    else
    {
      if ( CompareStringW(0x7Fu, 1u, v1, 4, v31, 4) != 2 )
      {
LABEL_37:
        if ( !(unsigned int)CPath::IsEmpty((CPath *)v24) )
        {
          ConstBuffer = CPath::_GetConstBuffer((CPath *)v24);
          CscUtil_CreateStringCopy(ConstBuffer, a1);
LABEL_40:
          v5 = 0;
          CPath::~CPath(v24);
          goto LABEL_4;
        }
LABEL_39:
        *a1 = v1;
        v1 = 0;
        goto LABEL_40;
      }
      v17 = CPath::Copy((CPath *)v24, v1 + 4);
    }
    if ( v17 < 0 )
      goto LABEL_39;
    goto LABEL_37;
  }
  v5 = -2147024882;
LABEL_4:
  CscUtil_HeapFree(v1, v4);
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v6 = L"<null>";
    if ( *a1 )
      v6 = *a1;
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      46,
      (unsigned int)WPP_640353d05de230bd321f309b7bf8540c_Traceguids,
      v5,
      (__int64)v6);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000ca48  mov     [rsp-8+arg_8], rbx
0x18000ca4d  mov     [rsp-8+arg_10], rsi
0x18000ca52  push    rbp
0x18000ca53  push    rdi
0x18000ca54  push    r12
0x18000ca56  push    r14
0x18000ca58  push    r15
0x18000ca5a  lea     rbp, [rsp-1B0h]
0x18000ca62  sub     rsp, 2B0h
0x18000ca69  mov     rax, cs:__security_cookie
0x18000ca70  xor     rax, rsp
0x18000ca73  mov     [rbp+1D0h+var_28], rax
0x18000ca7a  xor     ebx, ebx
0x18000ca7c  mov     qword ptr [rcx], 0
0x18000ca83  mov     qword ptr [rbp+1D0h+var_50], rbx
0x18000ca8a  mov     r12, rcx
0x18000ca8d  call    cs:__imp_GetProcessHeap
0x18000ca93  xor     edx, edx
0x18000ca95  mov     edi, 8000FFFFh
0x18000ca9a  test    rax, rax
0x18000ca9d  mov     ecx, 208h
0x18000caa2  cmovnz  edi, edx
0x18000caa5  jz      loc_18000CB53
0x18000caab  mov     r8d, ecx; dwBytes
0x18000caae  lea     edx, [rbx+8]; dwFlags
0x18000cab1  mov     rcx, rax; hHeap
0x18000cab4  call    cs:__imp_HeapAlloc
0x18000caba  mov     qword ptr [rbp+1D0h+var_50], rax
0x18000cac1  mov     rbx, rax
0x18000cac4  test    rax, rax
0x18000cac7  jnz     loc_18000CB4E
0x18000cacd  mov     edi, 8007000Eh
0x18000cad2  lea     rsi, WPP_GLOBAL_Control
0x18000cad9  mov     rcx, rbx; lpMem
0x18000cadc  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18000cae1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cae8  cmp     rcx, rsi
0x18000caeb  jz      short loc_18000CB21
0x18000caed  test    byte ptr [rcx+1Ch], 8
0x18000caf1  jz      short loc_18000CB21
0x18000caf3  cmp     qword ptr [r12], 0
0x18000caf8  lea     rax, aNull; "<null>"
0x18000caff  mov     rcx, [rcx+10h]
0x18000cb03  lea     r8, WPP_640353d05de230bd321f309b7bf8540c_Traceguids
0x18000cb0a  cmovnz  rax, [r12]
0x18000cb0f  mov     edx, 2Eh ; '.'
0x18000cb14  mov     r9d, edi
0x18000cb17  mov     [rsp+2D0h+lpString2], rax
0x18000cb1c  call    WPP_SF_dS
0x18000cb21  mov     eax, edi
0x18000cb23  mov     rcx, [rbp+1D0h+var_28]
0x18000cb2a  xor     rcx, rsp; StackCookie
0x18000cb2d  call    __security_check_cookie
0x18000cb32  lea     r11, [rsp+2D0h+var_20]
0x18000cb3a  mov     rbx, [r11+38h]
0x18000cb3e  mov     rsi, [r11+40h]
0x18000cb42  mov     rsp, r11
0x18000cb45  pop     r15
0x18000cb47  pop     r14
0x18000cb49  pop     r12
0x18000cb4b  pop     rdi
0x18000cb4c  pop     rbp
0x18000cb4d  retn
0x18000cb4e  mov     ecx, 208h
0x18000cb53  test    edi, edi
0x18000cb55  js      loc_18000CAD2
0x18000cb5b  xor     esi, esi
0x18000cb5d  xorps   xmm0, xmm0
0x18000cb60  cmp     cs:CscUmpLibraryState, esi
0x18000cb66  movzx   r14d, cx
0x18000cb6a  movups  xmmword ptr [rbp+1D0h+String2], xmm0
0x18000cb71  mov     [rbp+1D0h+String2+2], cx
0x18000cb78  mov     r15, rbx
0x18000cb7b  mov     qword ptr [rbp+1D0h+String2+8], rbx
0x18000cb82  mov     [rsp+2D0h+var_2A0], si
0x18000cb87  jnz     short loc_18000CBBC
0x18000cb89  mov     edi, 0C0000184h
0x18000cb8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb95  lea     rsi, WPP_GLOBAL_Control
0x18000cb9c  cmp     rcx, rsi
0x18000cb9f  jz      loc_18000CC38
0x18000cba5  test    byte ptr [rcx+1Ch], 2
0x18000cba9  jz      loc_18000CC38
0x18000cbaf  mov     edx, 2Dh ; '-'
0x18000cbb4  mov     r9d, edi
0x18000cbb7  jmp     loc_18000CDD9
0x18000cbbc  lea     rcx, [rsp+2D0h+FileHandle]
0x18000cbc1  mov     [rsp+2D0h+FileHandle], rsi
0x18000cbc6  call    CscDriverpReferenceControlHandle
0x18000cbcb  mov     edi, eax
0x18000cbcd  test    eax, eax
0x18000cbcf  js      short loc_18000CC07
0x18000cbd1  mov     rcx, [rsp+2D0h+FileHandle]; FileHandle
0x18000cbd6  lea     r8, [rsp+2D0h+var_2A0]
0x18000cbdb  lea     rdx, [rbp+1D0h+String2]
0x18000cbe2  call    CscDriverpQueryLocationDatabaseFsControl
0x18000cbe7  lea     rcx, [rsp+2D0h+FileHandle]
0x18000cbec  mov     edi, eax
0x18000cbee  call    CscDriverpDereferenceControlHandle
0x18000cbf3  movzx   esi, [rsp+2D0h+var_2A0]
0x18000cbf8  mov     r15, qword ptr [rbp+1D0h+String2+8]
0x18000cbff  movzx   r14d, [rbp+1D0h+String2+2]
0x18000cc07  test    edi, edi
0x18000cc09  js      loc_18000CD4E
0x18000cc0f  movzx   ecx, [rbp+1D0h+String2]
0x18000cc16  movzx   eax, r14w
0x18000cc1a  sub     rax, rcx
0x18000cc1d  cmp     rax, 2
0x18000cc21  jb      loc_18000CD5A
0x18000cc27  shr     rcx, 1
0x18000cc2a  xor     eax, eax
0x18000cc2c  mov     [r15+rcx*2], ax
0x18000cc31  lea     rsi, WPP_GLOBAL_Control
0x18000cc38  test    edi, edi
0x18000cc3a  jnz     loc_18000CE68
0x18000cc40  movzx   eax, word ptr cs:asc_18008FE08+8; ""
0x18000cc47  lea     r9d, [rdi+0Bh]; cchCount1
0x18000cc4b  movups  xmm0, xmmword ptr cs:aSystemroot; "\\SystemRoot"
0x18000cc52  lea     edi, [r9-0Ah]
0x18000cc56  mov     [rbp+1D0h+var_48], ax
0x18000cc5d  movsd   xmm1, qword ptr cs:aSystemroot+10h; "oot"
0x18000cc65  lea     rax, [rsp+2D0h+var_290]
0x18000cc6a  mov     [rbp+1D0h+var_78], rax
0x18000cc71  lea     r14d, [r9+74h]
0x18000cc75  mov     ecx, 208h
0x18000cc7a  mov     [rsp+2D0h+cchCount2], r9d; cchCount2
0x18000cc7f  lea     rax, [rsp+2D0h+var_290]
0x18000cc84  mov     [rbp+1D0h+var_68], rcx
0x18000cc8b  mov     [rbp+1D0h+var_70], rax
0x18000cc92  mov     r8, rbx; lpString1
0x18000cc95  lea     rax, [rsp+2D0h+var_290]
0x18000cc9a  mov     [rbp+1D0h+var_60], rcx
0x18000cca1  mov     [rbp+1D0h+var_80], rax
0x18000cca8  mov     edx, edi; dwCmpFlags
0x18000ccaa  xor     eax, eax
0x18000ccac  movsd   [rbp+1D0h+var_30], xmm1
0x18000ccb4  mov     [rsp+2D0h+var_290], ax
0x18000ccb9  mov     ecx, r14d; Locale
0x18000ccbc  movups  xmmword ptr [rbp+1D0h+String2], xmm0
0x18000ccc3  lea     rax, [rbp+1D0h+String2]
0x18000ccca  mov     [rbp+1D0h+var_88], 2080000h
0x18000ccd4  movsd   xmm0, qword ptr cs:asc_18008FE08; "\\??\\"
0x18000ccdc  mov     [rsp+2D0h+lpString2], rax; lpString2
0x18000cce1  movsd   qword ptr [rbp+1D0h+var_50], xmm0
0x18000cce9  call    cs:__imp_CompareStringW
0x18000ccef  cmp     eax, 2
0x18000ccf2  jnz     loc_18000CDEE
0x18000ccf8  lea     rdx, [rsp+2D0h+FileHandle]; unsigned __int16 **
0x18000ccfd  mov     [rsp+2D0h+FileHandle], 0
0x18000cd06  lea     rcx, aSystemroot_0; "%SystemRoot%"
0x18000cd0d  call    ?CscUtil_ExpandEnvironmentStringsAlloc@@YAJPEBGPEAPEAG@Z; CscUtil_ExpandEnvironmentStringsAlloc(ushort const *,ushort * *)
0x18000cd12  test    eax, eax
0x18000cd14  js      loc_18000CE51
0x18000cd1a  mov     rdx, [rsp+2D0h+FileHandle]; unsigned __int16 *
0x18000cd1f  lea     rcx, [rsp+2D0h+var_290]; this
0x18000cd24  call    ?Copy@CPath@@QEAAJPEBG@Z; CPath::Copy(ushort const *)
0x18000cd29  mov     edi, eax
0x18000cd2b  test    eax, eax
0x18000cd2d  js      short loc_18000CD3F
0x18000cd2f  lea     rdx, [rbx+16h]; unsigned __int16 *
0x18000cd33  lea     rcx, [rsp+2D0h+var_290]; this
0x18000cd38  call    ?Append@CPath@@QEAAJPEBG@Z; CPath::Append(ushort const *)
0x18000cd3d  mov     edi, eax
0x18000cd3f  mov     rcx, [rsp+2D0h+FileHandle]; lpMem
0x18000cd44  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18000cd49  jmp     loc_18000CE28
0x18000cd4e  cmp     edi, 80000005h
0x18000cd54  jnz     loc_18000CB8E
0x18000cd5a  movzx   ecx, si; dwBytes
0x18000cd5d  lea     r9, [rbp+1D0h+var_50]; void **
0x18000cd64  mov     r8, rbx; void *
0x18000cd67  call    ?CscUtil_HeapReAlloc@@YAJ_KHPEAXPEAPEAX1@Z; CscUtil_HeapReAlloc(unsigned __int64,int,void *,void * *,void *)
0x18000cd6c  mov     rbx, qword ptr [rbp+1D0h+var_50]
0x18000cd73  mov     edi, eax
0x18000cd75  test    eax, eax
0x18000cd77  js      loc_18000CAD2
0x18000cd7d  xorps   xmm0, xmm0
0x18000cd80  lea     rdx, [rsp+2D0h+var_2A0]
0x18000cd85  movups  xmmword ptr [rbp+1D0h+String2], xmm0
0x18000cd8c  lea     rcx, [rbp+1D0h+String2]
0x18000cd93  mov     [rbp+1D0h+String2+2], si
0x18000cd9a  mov     qword ptr [rbp+1D0h+String2+8], rbx
0x18000cda1  call    CscUmQueryDatabaseLocation
0x18000cda6  mov     edi, eax
0x18000cda8  test    eax, eax
0x18000cdaa  jns     loc_18000CC31
0x18000cdb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdb7  lea     rsi, WPP_GLOBAL_Control
0x18000cdbe  cmp     rcx, rsi
0x18000cdc1  jz      loc_18000CC38
0x18000cdc7  test    byte ptr [rcx+1Ch], 2
0x18000cdcb  jz      loc_18000CC38
0x18000cdd1  mov     edx, 2Ch ; ','
0x18000cdd6  mov     r9d, eax
0x18000cdd9  mov     rcx, [rcx+10h]
0x18000cddd  lea     r8, WPP_640353d05de230bd321f309b7bf8540c_Traceguids
0x18000cde4  call    WPP_SF_d
0x18000cde9  jmp     loc_18000CC38
0x18000cdee  mov     r9d, 4; cchCount1
0x18000cdf4  lea     rax, [rbp+1D0h+var_50]
0x18000cdfb  mov     [rsp+2D0h+cchCount2], r9d; cchCount2
0x18000ce00  mov     r8, rbx; lpString1
0x18000ce03  mov     edx, edi; dwCmpFlags
0x18000ce05  mov     [rsp+2D0h+lpString2], rax; lpString2
0x18000ce0a  mov     ecx, r14d; Locale
0x18000ce0d  call    cs:__imp_CompareStringW
0x18000ce13  cmp     eax, 2
0x18000ce16  jnz     short loc_18000CE2C
0x18000ce18  lea     rdx, [rbx+8]; unsigned __int16 *
0x18000ce1c  lea     rcx, [rsp+2D0h+var_290]; this
0x18000ce21  call    ?Copy@CPath@@QEAAJPEBG@Z; CPath::Copy(ushort const *)
0x18000ce26  mov     edi, eax
0x18000ce28  test    edi, edi
0x18000ce2a  js      short loc_18000CE51
0x18000ce2c  lea     rcx, [rsp+2D0h+var_290]; this
0x18000ce31  call    ?IsEmpty@CPath@@QEAAHXZ; CPath::IsEmpty(void)
0x18000ce36  test    eax, eax
0x18000ce38  jnz     short loc_18000CE51
0x18000ce3a  lea     rcx, [rsp+2D0h+var_290]; this
0x18000ce3f  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18000ce44  mov     rcx, rax; unsigned __int16 *
0x18000ce47  mov     rdx, r12; unsigned __int16 **
0x18000ce4a  call    ?CscUtil_CreateStringCopy@@YAJPEBGPEAPEAG@Z; CscUtil_CreateStringCopy(ushort const *,ushort * *)
0x18000ce4f  jmp     short loc_18000CE57
0x18000ce51  mov     [r12], rbx
0x18000ce55  xor     ebx, ebx
0x18000ce57  xor     edi, edi
0x18000ce59  lea     rcx, [rsp+2D0h+var_290]; this
0x18000ce5e  call    ??1CPath@@QEAA@XZ; CPath::~CPath(void)
0x18000ce63  jmp     loc_18000CAD9
0x18000ce68  mov     ecx, edi; int
0x18000ce6a  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x18000ce6f  mov     edi, eax
0x18000ce71  jmp     loc_18000CAD9
```
