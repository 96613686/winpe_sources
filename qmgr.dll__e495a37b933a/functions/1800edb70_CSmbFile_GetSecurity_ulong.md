# CSmbFile::GetSecurity(ulong)

- ea: `0x1800edb70`
- end: `0x1800ede76`
- name: `?GetSecurity@CSmbFile@@UEAAPEAXK@Z`
- size: `774`
- prototype: `void *__fastcall(CSmbFile *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180006640`
- `0x180008b70`
- `0x18000f5f0`
- `0x18009e9c8`
- `0x1800a7558`
- `0x1800edb70`
- `0x1800f9948`
- `0x1800f9960`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ede1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ede1e`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1800edcd4`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1800edcd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800edd80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ede46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800edd80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ede46`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800edd52`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800edd52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800edd02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800edd64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800edd02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800edd64`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1800edc33`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1800edc33`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall CSmbFile::GetSecurity(HANDLE *this, int a2)
{
  char v2; // bl
  void *result; // rax
  __int16 v5; // di
  int v6; // eax
  int v7; // r14d
  int v8; // ecx
  int v9; // r15d
  SECURITY_INFORMATION v10; // r8d
  int v11; // ebx
  signed int SecurityInfo; // eax
  __int16 v13; // di
  __int16 v14; // ax
  __int16 v15; // dx
  __int16 v16; // ax
  ULONG v17; // eax
  ULONG v18; // edi
  void *v19; // rbx
  void *v20; // rdi
  DWORD LastError; // eax
  signed int v22; // ebx
  DWORD v23; // eax
  void **pExceptionObject; // [rsp+40h] [rbp-138h] BYREF
  __int128 v25; // [rsp+48h] [rbp-130h]
  signed int v26; // [rsp+58h] [rbp-120h]
  int v27; // [rsp+5Ch] [rbp-11Ch]
  int v28; // [rsp+60h] [rbp-118h]
  void **v29; // [rsp+A0h] [rbp-D8h] BYREF
  __int128 v30; // [rsp+A8h] [rbp-D0h]
  signed int v31; // [rsp+B8h] [rbp-C0h]
  int v32; // [rsp+BCh] [rbp-BCh]
  int v33; // [rsp+C0h] [rbp-B8h]
  void **v34[7]; // [rsp+100h] [rbp-78h] BYREF
  ComError *v35; // [rsp+138h] [rbp-40h] BYREF
  ComError *v36; // [rsp+140h] [rbp-38h] BYREF
  DWORD dwBufferLength; // [rsp+188h] [rbp+10h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+190h] [rbp+18h] BYREF

  v2 = a2;
  SecurityDescriptor = 0;
  if ( !a2 )
    return 0;
  CNestedImpersonation::CNestedImpersonation((CNestedImpersonation *)v34, (const struct TokenHandle *)(this + 50));
  v5 = v2 & 1;
  v6 = v2 & 1 | 2;
  v7 = v2 & 2;
  if ( (v2 & 2) == 0 )
    v6 = v2 & 1;
  v8 = v6 | 4;
  v9 = v2 & 4;
  if ( (v2 & 4) == 0 )
    v8 = v6;
  v10 = v8 | 8;
  v11 = v2 & 8;
  if ( !v11 )
    v10 = v8;
  SecurityInfo = GetSecurityInfo(this[40], SE_FILE_OBJECT, v10, 0, 0, 0, 0, &SecurityDescriptor);
  if ( SecurityInfo )
  {
    if ( SecurityInfo > 0 )
      SecurityInfo = (unsigned __int16)SecurityInfo | 0x80070000;
    v25 = 0;
    pExceptionObject = &ComError::`vftable';
    v26 = SecurityInfo;
    v27 = 0;
    v28 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v13 = v5 ^ 1;
  v14 = v13 | 2;
  if ( v7 )
    v14 = v13;
  v15 = v14 | 8;
  if ( v9 )
    v15 = v14;
  *((_WORD *)SecurityDescriptor + 1) &= 0xFFD4u;
  v16 = v15 | 0x20;
  if ( v11 )
    v16 = v15;
  *((_WORD *)SecurityDescriptor + 1) |= v16;
  if ( *((__int16 *)SecurityDescriptor + 1) >= 0 )
  {
    try
    {
      dwBufferLength = 1024;
      while ( 1 )
      {
        v20 = operator new(dwBufferLength);
        if ( MakeSelfRelativeSD(SecurityDescriptor, v20, &dwBufferLength) )
          break;
        LastError = GetLastError();
        v22 = LastError;
        if ( LastError != 122 )
        {
          if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              26,
              WPP_544ed435ee403dfadff71ae516532c05_Traceguids,
              LastError);
          if ( v22 > 0 )
            v22 = (unsigned __int16)v22 | 0x80070000;
          v30 = 0;
          v29 = &ComError::`vftable';
          v31 = v22;
          v32 = 0;
          v33 = 1;
          throw (ComError *)&v29;
        }
        if ( v20
          && !HeapFree(hBitsHeap, 0, v20)
          && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v23 = GetLastError();
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, v20, v23);
        }
      }
      LocalFree(SecurityDescriptor);
      CNestedImpersonation::~CNestedImpersonation(v34);
      result = v20;
    }
    catch ( ComError *v36 )
    {
      LocalFree(SecurityDescriptor);
      throw;
    }
  }
  else
  {
    v17 = RtlLengthSecurityDescriptor(SecurityDescriptor);
    try
    {
      v18 = v17;
      v19 = operator new(v17);
      memcpy_0(v19, SecurityDescriptor, v18);
      LocalFree(SecurityDescriptor);
      CNestedImpersonation::~CNestedImpersonation(v34);
      result = v19;
    }
    catch ( ComError *v35 )
    {
      LocalFree(SecurityDescriptor);
      throw;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800edb70  mov     rax, rsp
0x1800edb73  mov     [rax+8], rbx
0x1800edb77  mov     [rax+20h], rsi
0x1800edb7b  push    rdi
0x1800edb7c  push    r12
0x1800edb7e  push    r13
0x1800edb80  push    r14
0x1800edb82  push    r15
0x1800edb84  sub     rsp, 150h
0x1800edb8b  mov     ebx, edx
0x1800edb8d  mov     rsi, rcx
0x1800edb90  xor     r12d, r12d
0x1800edb93  mov     [rax+18h], r12
0x1800edb97  test    edx, edx
0x1800edb99  jnz     short loc_1800EDBBA
0x1800edb9b  xor     eax, eax
0x1800edb9d  lea     r11, [rsp+178h+var_28]
0x1800edba5  mov     rbx, [r11+30h]
0x1800edba9  mov     rsi, [r11+48h]
0x1800edbad  mov     rsp, r11
0x1800edbb0  pop     r15
0x1800edbb2  pop     r14
0x1800edbb4  pop     r13
0x1800edbb6  pop     r12
0x1800edbb8  pop     rdi
0x1800edbb9  retn
0x1800edbba  lea     rdx, [rcx+190h]; struct TokenHandle *
0x1800edbc1  lea     rcx, [rsp+178h+var_78]; this
0x1800edbc9  call    ??0CNestedImpersonation@@QEAA@AEBVTokenHandle@@@Z; CNestedImpersonation::CNestedImpersonation(TokenHandle const &)
0x1800edbce  nop
0x1800edbcf  mov     edi, ebx
0x1800edbd1  mov     r13d, 1
0x1800edbd7  and     edi, r13d
0x1800edbda  mov     r14d, ebx
0x1800edbdd  lea     ecx, [r13+1]
0x1800edbe1  mov     eax, edi
0x1800edbe3  or      eax, ecx
0x1800edbe5  and     r14d, ecx
0x1800edbe8  cmovz   eax, edi
0x1800edbeb  mov     r15d, ebx
0x1800edbee  mov     ecx, eax
0x1800edbf0  or      ecx, 4
0x1800edbf3  and     r15d, 4
0x1800edbf7  cmovz   ecx, eax
0x1800edbfa  lea     eax, [r13+7]
0x1800edbfe  mov     r8d, ecx
0x1800edc01  or      r8d, eax
0x1800edc04  and     ebx, eax
0x1800edc06  cmovz   r8d, ecx; SecurityInfo
0x1800edc0a  lea     rax, [rsp+178h+SecurityDescriptor]
0x1800edc12  mov     [rsp+178h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1800edc17  mov     [rsp+178h+ppSacl], r12; ppSacl
0x1800edc1c  mov     [rsp+178h+ppDacl], r12; ppDacl
0x1800edc21  mov     [rsp+178h+ppsidGroup], r12; ppsidGroup
0x1800edc26  xor     r9d, r9d; ppsidOwner
0x1800edc29  mov     edx, r13d; ObjectType
0x1800edc2c  mov     rcx, [rsi+140h]; handle
0x1800edc33  call    cs:__imp_GetSecurityInfo
0x1800edc39  test    eax, eax
0x1800edc3b  jz      short loc_1800EDC7B
0x1800edc3d  jle     short loc_1800EDC47
0x1800edc3f  movzx   eax, ax
0x1800edc42  or      eax, 80070000h
0x1800edc47  xorps   xmm0, xmm0
0x1800edc4a  movups  [rsp+178h+var_130], xmm0
0x1800edc4f  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800edc56  mov     [rsp+178h+pExceptionObject], rcx
0x1800edc5b  mov     [rsp+178h+var_120], eax
0x1800edc5f  mov     [rsp+178h+var_11C], r12d
0x1800edc64  mov     [rsp+178h+var_118], r13d
0x1800edc69  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800edc70  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x1800edc75  call    _CxxThrowException_0
0x1800edc7b  xor     di, r13w
0x1800edc7f  movzx   eax, di
0x1800edc82  or      ax, 2
0x1800edc86  test    r14d, r14d
0x1800edc89  cmovnz  ax, di
0x1800edc8d  movzx   edx, ax
0x1800edc90  or      dx, 8
0x1800edc94  test    r15d, r15d
0x1800edc97  cmovnz  dx, ax
0x1800edc9b  mov     rax, [rsp+178h+SecurityDescriptor]
0x1800edca3  mov     ecx, 0FFD4h
0x1800edca8  and     [rax+2], cx
0x1800edcac  mov     rcx, [rsp+178h+SecurityDescriptor]
0x1800edcb4  movzx   eax, dx
0x1800edcb7  or      ax, 20h
0x1800edcbb  test    ebx, ebx
0x1800edcbd  cmovnz  ax, dx
0x1800edcc1  or      [rcx+2], ax
0x1800edcc5  mov     rcx, [rsp+178h+SecurityDescriptor]; SecurityDescriptor
0x1800edccd  cmp     [rcx+2], r12w
0x1800edcd2  jge     short loc_1800EDD1E
0x1800edcd4  call    cs:__imp_RtlLengthSecurityDescriptor
0x1800edcda  nop
0x1800edcdb  mov     edi, eax
0x1800edcdd  mov     ecx, eax; dwBytes
0x1800edcdf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800edce4  mov     rbx, rax
0x1800edce7  mov     r8d, edi; Size
0x1800edcea  mov     rdx, [rsp+178h+SecurityDescriptor]; Src
0x1800edcf2  mov     rcx, rax; void *
0x1800edcf5  call    memcpy_0
0x1800edcfa  mov     rcx, [rsp+178h+SecurityDescriptor]; hMem
0x1800edd02  call    cs:__imp_LocalFree
0x1800edd08  nop
0x1800edd09  lea     rcx, [rsp+178h+var_78]; this
0x1800edd11  call    ??1CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::~CNestedImpersonation(void)
0x1800edd16  mov     rax, rbx
0x1800edd19  jmp     loc_1800EDB9D
0x1800edd1e  mov     [rsp+178h+dwBufferLength], 400h
0x1800edd29  lea     rsi, WPP_GLOBAL_Control
0x1800edd30  mov     ecx, [rsp+178h+dwBufferLength]; dwBytes
0x1800edd37  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800edd3c  mov     rdi, rax
0x1800edd3f  lea     r8, [rsp+178h+dwBufferLength]; lpdwBufferLength
0x1800edd47  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x1800edd4a  mov     rcx, [rsp+178h+SecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1800edd52  call    cs:__imp_MakeSelfRelativeSD
0x1800edd58  test    eax, eax
0x1800edd5a  jz      short loc_1800EDD80
0x1800edd5c  mov     rcx, [rsp+178h+SecurityDescriptor]; hMem
0x1800edd64  call    cs:__imp_LocalFree
0x1800edd6a  nop
0x1800edd6b  lea     rcx, [rsp+178h+var_78]; this
0x1800edd73  call    ??1CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::~CNestedImpersonation(void)
0x1800edd78  mov     rax, rdi
0x1800edd7b  jmp     loc_1800EDB9D
0x1800edd80  call    cs:__imp_GetLastError
0x1800edd86  mov     ebx, eax
0x1800edd88  cmp     eax, 7Ah ; 'z'
0x1800edd8b  jz      short loc_1800EDE09
0x1800edd8d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800edd94  cmp     rcx, rsi
0x1800edd97  jz      short loc_1800EDDB7
0x1800edd99  test    byte ptr [rcx+1Ch], 4
0x1800edd9d  jz      short loc_1800EDDB7
0x1800edd9f  mov     edx, 1Ah
0x1800edda4  mov     r9d, eax
0x1800edda7  lea     r8, WPP_544ed435ee403dfadff71ae516532c05_Traceguids
0x1800eddae  mov     rcx, [rcx+10h]
0x1800eddb2  call    WPP_SF_d
0x1800eddb7  test    ebx, ebx
0x1800eddb9  jle     short loc_1800EDDC4
0x1800eddbb  movzx   ebx, bx
0x1800eddbe  or      ebx, 80070000h
0x1800eddc4  xorps   xmm0, xmm0
0x1800eddc7  movups  [rsp+178h+var_D0], xmm0
0x1800eddcf  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800eddd6  mov     [rsp+178h+var_D8], rcx
0x1800eddde  mov     [rsp+178h+var_C0], ebx
0x1800edde5  mov     [rsp+178h+var_BC], r12d
0x1800edded  mov     [rsp+178h+var_B8], r13d
0x1800eddf5  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800eddfc  lea     rcx, [rsp+178h+var_D8]; pExceptionObject
0x1800ede04  call    _CxxThrowException_0
0x1800ede09  test    rdi, rdi
0x1800ede0c  jz      loc_1800EDD30
0x1800ede12  mov     r8, rdi; lpMem
0x1800ede15  xor     edx, edx; dwFlags
0x1800ede17  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x1800ede1e  call    cs:__imp_HeapFree
0x1800ede24  test    eax, eax
0x1800ede26  jnz     loc_1800EDD30
0x1800ede2c  mov     rax, cs:WPP_GLOBAL_Control
0x1800ede33  cmp     rax, rsi
0x1800ede36  jz      loc_1800EDD30
0x1800ede3c  test    byte ptr [rax+1Ch], 4
0x1800ede40  jz      loc_1800EDD30
0x1800ede46  call    cs:__imp_GetLastError
0x1800ede4c  mov     edx, 0Bh
0x1800ede51  mov     dword ptr [rsp+178h+ppsidGroup], eax
0x1800ede55  mov     r9, rdi
0x1800ede58  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x1800ede5f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ede66  mov     rcx, [rcx+10h]
0x1800ede6a  call    WPP_SF_qD
0x1800ede6f  jmp     loc_1800EDD30
```
