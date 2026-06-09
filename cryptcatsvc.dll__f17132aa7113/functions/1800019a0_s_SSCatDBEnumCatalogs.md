# s_SSCatDBEnumCatalogs

- ea: `0x1800019a0`
- end: `0x180001cd0`
- name: `s_SSCatDBEnumCatalogs`
- size: `816`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800019a0`
- `0x180001ce0`
- `0x18000a59c`
- `0x18000be40`
- `0x18001998c`
- `0x180019a08`
- `0x18001ac64`
- `0x18001ad58`
- `0x18001f748`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a9d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001a81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001a81`
- `ntdll!EtwEventWrite` at `0x180001b62`
- `ntdll!EtwEventWrite` at `0x180001c0c`
- `ntdll!EtwEventWrite` at `0x180001b62`
- `ntdll!EtwEventWrite` at `0x180001c0c`
- `ntdll!EtwEventEnabled` at `0x180001ad4`
- `ntdll!EtwEventEnabled` at `0x180001bca`
- `ntdll!EtwEventEnabled` at `0x180001ad4`
- `ntdll!EtwEventEnabled` at `0x180001bca`

## pseudocode

```c
__int64 __fastcall s_SSCatDBEnumCatalogs(
        __int64 a1,
        __int16 *a2,
        int a3,
        unsigned int a4,
        __int64 a5,
        _DWORD *a6,
        int a7)
{
  int v7; // r10d
  char v8; // di
  __int64 v12; // rsi
  __int64 v13; // r15
  __int16 *v14; // rdx
  const wchar_t *v15; // r8
  __int16 v16; // ax
  wchar_t v17; // cx
  unsigned int v18; // edx
  unsigned __int16 *v19; // rcx
  DWORD LastError; // ebx
  wchar_t *v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rax
  bool v24; // zf
  int i; // esi
  unsigned int v26; // eax
  unsigned int v28; // edx
  unsigned __int16 *v29; // rcx
  __int64 v30; // rax
  unsigned int v31; // eax
  int v32; // [rsp+28h] [rbp-69h]
  int v33; // [rsp+28h] [rbp-69h]
  __int64 v34; // [rsp+30h] [rbp-61h]
  DWORD v35; // [rsp+40h] [rbp-51h] BYREF
  __int64 v36; // [rsp+48h] [rbp-49h] BYREF
  DWORD *v37; // [rsp+50h] [rbp-41h] BYREF
  __int64 v38; // [rsp+58h] [rbp-39h]
  __int64 *v39; // [rsp+60h] [rbp-31h]
  __int64 v40; // [rsp+68h] [rbp-29h]
  DWORD *v41; // [rsp+70h] [rbp-21h]
  __int64 v42; // [rsp+78h] [rbp-19h]
  __int64 v43; // [rsp+80h] [rbp-11h]
  int v44; // [rsp+88h] [rbp-9h]
  int v45; // [rsp+8Ch] [rbp-5h]

  v7 = a7;
  v8 = 0;
  v36 = a5;
  v12 = 0;
  v13 = a3;
  v34 = 0;
  if ( HIDWORD(qword_180032708) )
  {
    v12 = CatDBQueryPerformanceCounter();
    v7 = a7;
    v34 = v12;
  }
  if ( !a1 || (unsigned int)v13 > 1 || *((_DWORD *)&off_180023000 + 16 * v13 + 2) != a4 || !a2 )
  {
LABEL_17:
    SetLastError(0xA0u);
    ErrLog_LogError(v19, v18, 0xE18u, 0, 0, v32);
    goto LABEL_18;
  }
  v14 = a2;
  v15 = L"{00000000-0000-0000-0000-000000000000}";
  while ( 1 )
  {
    v16 = *v14;
    v17 = *v15;
    if ( !*v14 )
      break;
    if ( v17 == 48 )
    {
      if ( (unsigned __int16)(v16 - 48) <= 9u || (unsigned __int16)(v16 - 97) <= 5u )
        goto LABEL_15;
      if ( (unsigned __int16)(v16 - 65) > 5u )
        goto LABEL_17;
      ++v14;
      ++v15;
    }
    else
    {
      if ( v17 != v16 )
        goto LABEL_17;
LABEL_15:
      ++v14;
      ++v15;
    }
  }
  if ( v17 )
    goto LABEL_17;
  LOWORD(v35) = a4;
  if ( qword_180032A08 )
  {
    v21 = (&off_180023000)[8 * v13];
    if ( (unsigned __int8)EtwEventEnabled(qword_180032A08, "\b ") )
    {
      v22 = -1;
      v37 = (DWORD *)a2;
      v23 = -1;
      do
        v24 = a2[++v23] == 0;
      while ( !v24 );
      v38 = (unsigned int)(2 * v23 + 2);
      v39 = (__int64 *)v21;
      do
        v24 = v21[++v22] == 0;
      while ( !v24 );
      v40 = (unsigned int)(2 * v22 + 2);
      v42 = 2;
      v41 = &v35;
      v43 = v36;
      v44 = (unsigned __int16)v35;
      v45 = 0;
      EtwEventWrite(qword_180032A08, "\b ", 4, &v37);
    }
    v7 = a7;
  }
  v8 = 1;
  for ( i = 0; ; i = 1 )
  {
    v33 = v7;
    v26 = _CatDBEnumCatalogs(a2, (unsigned int)v13, a4);
    LastError = v26;
    if ( !v26 || i || !(unsigned int)_CatDBErrorIsCorruption(v26) )
    {
      v12 = v34;
      goto LABEL_32;
    }
    if ( !(unsigned int)_CatDBRecoverFromCorruption() )
      break;
    v7 = a7;
  }
  ErrLog_LogError(v29, v28, 0xE34u, 0, 0, v33);
  v12 = v34;
LABEL_18:
  LastError = GetLastError();
  if ( !LastError )
    LastError = -2147418113;
LABEL_32:
  if ( HIDWORD(qword_180032708) )
  {
    v30 = CatDBQueryPerformanceCounter();
    v31 = CatDBDeltaPerformanceCounterMicroseconds(v12, v30);
    ErrLog_LogPrintfW(0, 1, L"EnumCatalogs:: microseconds: %d", v31);
  }
  if ( v8 )
  {
    LODWORD(v36) = *a6;
    v35 = LastError;
    if ( qword_180032A08 )
    {
      if ( (unsigned __int8)EtwEventEnabled(qword_180032A08, "\t ") )
      {
        v37 = &v35;
        v38 = 4;
        v39 = &v36;
        v40 = 4;
        EtwEventWrite(qword_180032A08, "\t ", 2, &v37);
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800019a0  mov     [rsp-8+arg_0], rbx
0x1800019a5  push    rbp
0x1800019a6  push    rsi
0x1800019a7  push    rdi
0x1800019a8  push    r12
0x1800019aa  push    r13
0x1800019ac  push    r14
0x1800019ae  push    r15
0x1800019b0  lea     rbp, [rsp-0Fh]
0x1800019b5  sub     rsp, 0A0h
0x1800019bc  mov     rax, cs:__security_cookie
0x1800019c3  xor     rax, rsp
0x1800019c6  mov     [rbp+3Fh+var_40], rax
0x1800019ca  mov     r10, qword ptr [rbp+3Fh+arg_30]
0x1800019ce  xor     edi, edi
0x1800019d0  cmp     dword ptr cs:qword_180032708+4, edi
0x1800019d6  mov     r12d, r9d
0x1800019d9  mov     r9, [rbp+3Fh+arg_20]
0x1800019dd  mov     r14, rdx
0x1800019e0  mov     r13, [rbp+3Fh+arg_28]
0x1800019e4  mov     rbx, rcx
0x1800019e7  mov     [rbp+3Fh+var_88], r9
0x1800019eb  mov     esi, edi
0x1800019ed  movsxd  r15, r8d
0x1800019f0  mov     [rbp+3Fh+var_98], r10
0x1800019f4  mov     [rbp+3Fh+var_A0], rdi
0x1800019f8  jnz     loc_180001C3B
0x1800019fe  test    rbx, rbx
0x180001a01  jz      short loc_180001A7C
0x180001a03  cmp     r15d, 1
0x180001a07  ja      short loc_180001A7C
0x180001a09  mov     rbx, r15
0x180001a0c  lea     r11, off_180023000; "SHA1"
0x180001a13  shl     rbx, 6
0x180001a17  cmp     [rbx+r11+8], r12d
0x180001a1c  jnz     short loc_180001A7C
0x180001a1e  test    r14, r14
0x180001a21  jz      short loc_180001A7C
0x180001a23  mov     rdx, r14
0x180001a26  lea     r8, a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x180001a2d  nop     dword ptr [rax]
0x180001a30  movzx   eax, word ptr [rdx]
0x180001a33  movzx   ecx, word ptr [r8]
0x180001a37  test    ax, ax
0x180001a3a  jz      short loc_180001A77
0x180001a3c  cmp     cx, 30h ; '0'
0x180001a40  jnz     short loc_180001A68
0x180001a42  lea     ecx, [rax-30h]
0x180001a45  cmp     cx, 9
0x180001a49  jbe     short loc_180001A6D
0x180001a4b  lea     ecx, [rax-61h]
0x180001a4e  cmp     cx, 5
0x180001a52  jbe     short loc_180001A6D
0x180001a54  sub     ax, 41h ; 'A'
0x180001a58  cmp     ax, 5
0x180001a5c  ja      short loc_180001A7C
0x180001a5e  add     rdx, 2
0x180001a62  add     r8, 2
0x180001a66  jmp     short loc_180001A30
0x180001a68  cmp     cx, ax
0x180001a6b  jnz     short loc_180001A7C
0x180001a6d  add     rdx, 2
0x180001a71  add     r8, 2
0x180001a75  jmp     short loc_180001A30
0x180001a77  cmp     di, cx
0x180001a7a  jz      short loc_180001AB4
0x180001a7c  mov     ecx, 0A0h; dwErrCode
0x180001a81  call    cs:__imp_SetLastError
0x180001a87  xor     r9d, r9d; unsigned int
0x180001a8a  mov     [rsp+0D0h+var_B0], 0; int
0x180001a92  mov     r8d, 0E18h; unsigned int
0x180001a98  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180001a9d  call    cs:__imp_GetLastError
0x180001aa3  mov     ebx, eax
0x180001aa5  mov     eax, 8000FFFFh
0x180001aaa  test    ebx, ebx
0x180001aac  cmovz   ebx, eax
0x180001aaf  jmp     loc_180001B9B
0x180001ab4  mov     rcx, cs:qword_180032A08
0x180001abb  mov     word ptr [rbp+3Fh+var_90], r12w
0x180001ac0  test    rcx, rcx
0x180001ac3  jz      loc_180001B70
0x180001ac9  mov     rbx, [rbx+r11]
0x180001acd  lea     rdx, CAPI2_CATDB_ENUM_CATALOG_FROM_HASH_START_EVENT; "\b "
0x180001ad4  call    cs:__imp_EtwEventEnabled
0x180001ada  test    al, al
0x180001adc  jz      loc_180001B68
0x180001ae2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180001ae9  mov     [rbp+3Fh+var_80], r14
0x180001aed  mov     rax, rcx
0x180001af0  cmp     [r14+rax*2+2], di
0x180001af6  lea     rax, [rax+1]
0x180001afa  jnz     short loc_180001AF0
0x180001afc  lea     eax, ds:2[rax*2]
0x180001b03  mov     dword ptr [rbp+3Fh+var_78+4], edi
0x180001b06  mov     dword ptr [rbp+3Fh+var_78], eax
0x180001b09  mov     [rbp+3Fh+var_70], rbx
0x180001b0d  nop     dword ptr [rax]
0x180001b10  cmp     [rbx+rcx*2+2], di
0x180001b15  lea     rcx, [rcx+1]
0x180001b19  jnz     short loc_180001B10
0x180001b1b  lea     eax, ds:2[rcx*2]
0x180001b22  mov     dword ptr [rbp+3Fh+var_68+4], edi
0x180001b25  mov     rcx, cs:qword_180032A08
0x180001b2c  lea     r9, [rbp+3Fh+var_80]
0x180001b30  mov     dword ptr [rbp+3Fh+var_68], eax
0x180001b33  lea     rdx, CAPI2_CATDB_ENUM_CATALOG_FROM_HASH_START_EVENT; "\b "
0x180001b3a  lea     rax, [rbp+3Fh+var_90]
0x180001b3e  mov     [rbp+3Fh+var_58], 2
0x180001b46  mov     [rbp+3Fh+var_60], rax
0x180001b4a  mov     r8d, 4
0x180001b50  mov     rax, [rbp+3Fh+var_88]
0x180001b54  mov     [rbp+3Fh+var_50], rax
0x180001b58  movzx   eax, word ptr [rbp+3Fh+var_90]
0x180001b5c  mov     [rbp+3Fh+var_48], eax
0x180001b5f  mov     [rbp+3Fh+var_44], edi
0x180001b62  call    cs:__imp_EtwEventWrite
0x180001b68  mov     r10, [rbp+3Fh+var_98]
0x180001b6c  mov     r9, [rbp+3Fh+var_88]
0x180001b70  mov     dil, 1
0x180001b73  xor     esi, esi
0x180001b75  mov     qword ptr [rsp+0D0h+var_A8], r10; int
0x180001b7a  mov     r8d, r12d
0x180001b7d  mov     edx, r15d
0x180001b80  mov     qword ptr [rsp+0D0h+var_B0], r13
0x180001b85  mov     rcx, r14
0x180001b88  call    ?_CatDBEnumCatalogs@@YAKPEBGW4__MIDL_ICatDBSvc_0002@@KPEAEPEAKPEAPEAPEAG@Z; _CatDBEnumCatalogs(ushort const *,__MIDL_ICatDBSvc_0002,ulong,uchar *,ulong *,ushort * * *)
0x180001b8d  mov     ebx, eax
0x180001b8f  test    eax, eax
0x180001b91  jnz     loc_180001C54
0x180001b97  mov     rsi, [rbp+3Fh+var_A0]
0x180001b9b  cmp     dword ptr cs:qword_180032708+4, 0
0x180001ba2  jnz     loc_180001CA5
0x180001ba8  test    dil, dil
0x180001bab  jz      short loc_180001C12
0x180001bad  mov     rcx, cs:qword_180032A08
0x180001bb4  mov     eax, [r13+0]
0x180001bb8  mov     dword ptr [rbp+3Fh+var_88], eax
0x180001bbb  mov     [rbp+3Fh+var_90], ebx
0x180001bbe  test    rcx, rcx
0x180001bc1  jz      short loc_180001C12
0x180001bc3  lea     rdx, CAPI2_CATDB_ENUM_CATALOG_FROM_HASH_STOP_EVENT; "\t "
0x180001bca  call    cs:__imp_EtwEventEnabled
0x180001bd0  test    al, al
0x180001bd2  jz      short loc_180001C12
0x180001bd4  mov     rcx, cs:qword_180032A08
0x180001bdb  lea     rax, [rbp+3Fh+var_90]
0x180001bdf  mov     [rbp+3Fh+var_80], rax
0x180001be3  lea     r9, [rbp+3Fh+var_80]
0x180001be7  lea     rax, [rbp+3Fh+var_88]
0x180001beb  mov     [rbp+3Fh+var_78], 4
0x180001bf3  mov     r8d, 2
0x180001bf9  mov     [rbp+3Fh+var_70], rax
0x180001bfd  lea     rdx, CAPI2_CATDB_ENUM_CATALOG_FROM_HASH_STOP_EVENT; "\t "
0x180001c04  mov     [rbp+3Fh+var_68], 4
0x180001c0c  call    cs:__imp_EtwEventWrite
0x180001c12  mov     eax, ebx
0x180001c14  mov     rcx, [rbp+3Fh+var_40]
0x180001c18  xor     rcx, rsp; StackCookie
0x180001c1b  call    __security_check_cookie
0x180001c20  mov     rbx, [rsp+0D0h+arg_0]
0x180001c28  add     rsp, 0A0h
0x180001c2f  pop     r15
0x180001c31  pop     r14
0x180001c33  pop     r13
0x180001c35  pop     r12
0x180001c37  pop     rdi
0x180001c38  pop     rsi
0x180001c39  pop     rbp
0x180001c3a  retn
0x180001c3b  call    _CatDBQueryPerformanceCounter
0x180001c40  mov     r9, [rbp+3Fh+var_88]
0x180001c44  mov     rsi, rax
0x180001c47  mov     r10, [rbp+3Fh+var_98]
0x180001c4b  mov     [rbp+3Fh+var_A0], rax
0x180001c4f  jmp     loc_1800019FE
0x180001c54  test    esi, esi
0x180001c56  jnz     loc_180001B97
0x180001c5c  mov     ecx, eax; unsigned int
0x180001c5e  call    ?_CatDBErrorIsCorruption@@YAHK@Z; _CatDBErrorIsCorruption(ulong)
0x180001c63  test    eax, eax
0x180001c65  jz      loc_180001B97
0x180001c6b  call    ?_CatDBRecoverFromCorruption@@YAHXZ; _CatDBRecoverFromCorruption(void)
0x180001c70  test    eax, eax
0x180001c72  jz      short loc_180001C86
0x180001c74  mov     r9, [rbp+3Fh+var_88]
0x180001c78  mov     esi, 1
0x180001c7d  mov     r10, [rbp+3Fh+var_98]
0x180001c81  jmp     loc_180001B75
0x180001c86  xor     r9d, r9d; unsigned int
0x180001c89  mov     [rsp+0D0h+var_B0], 0; int
0x180001c91  mov     r8d, 0E34h; unsigned int
0x180001c97  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180001c9c  mov     rsi, [rbp+3Fh+var_A0]
0x180001ca0  jmp     loc_180001A9D
0x180001ca5  call    _CatDBQueryPerformanceCounter
0x180001caa  mov     rdx, rax
0x180001cad  mov     rcx, rsi
0x180001cb0  call    _CatDBDeltaPerformanceCounterMicroseconds
0x180001cb5  mov     r9d, eax
0x180001cb8  lea     r8, aEnumcatalogsMi; "EnumCatalogs:: microseconds: %d"
0x180001cbf  mov     edx, 1; int
0x180001cc4  xor     ecx, ecx; unsigned __int16 *
0x180001cc6  call    ?ErrLog_LogPrintfW@@YAXPEAGHPEBGZZ; ErrLog_LogPrintfW(ushort *,int,ushort const *,...)
0x180001ccb  jmp     loc_180001BA8
```
