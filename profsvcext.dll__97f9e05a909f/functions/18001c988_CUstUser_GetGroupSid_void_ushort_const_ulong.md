# CUstUser::_GetGroupSid(void *,ushort * * * const,ulong &)

- ea: `0x18001c988`
- end: `0x18001cc1d`
- name: `?_GetGroupSid@CUstUser@@KAJPEAXQEAPEAPEAGAEAK@Z`
- size: `661`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned __int16 ***const, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c64c`

## callees

- `0x18000baec`
- `0x18001afa0`
- `0x18001afc8`
- `0x18001b008`
- `0x18001c988`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c9d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ca38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cb74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cbc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c9d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ca38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cb74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cbc6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001cc08`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001cc08`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001c9ed`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001c9ed`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001c9c8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ca99`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001c9c8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ca99`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001cb33`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001cb33`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUstUser::_GetGroupSid(HANDLE TokenHandle, unsigned __int16 ***const a2, unsigned int *a3)
{
  unsigned int v6; // ebx
  _DWORD *v7; // rsi
  __int64 v8; // r9
  signed int LastError; // eax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rax
  unsigned __int16 **v12; // rax
  __int64 v13; // r9
  unsigned int i; // edi
  signed int v15; // eax
  signed int v16; // eax
  DWORD TokenInformationLength; // [rsp+78h] [rbp+10h] BYREF

  *a2 = 0;
  *a3 = 0;
  TokenInformationLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenGroups, 0, 0, &TokenInformationLength) && GetLastError() == 122 )
  {
    v6 = 0;
    v7 = GlobalAlloc(0x40u, TokenInformationLength);
    if ( !v7 )
    {
      v6 = -2147024882;
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids, v8);
      }
      return v6;
    }
    goto LABEL_13;
  }
  v7 = 0;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids, v6);
  }
  if ( (v6 & 0x80000000) == 0 )
  {
LABEL_13:
    if ( GetTokenInformation(TokenHandle, TokenGroups, v7, TokenInformationLength, &TokenInformationLength) )
    {
      v10 = (unsigned int)(*v7 + 1);
      *a3 = v10;
      v11 = 8 * v10;
      if ( !is_mul_ok(v10, 8u) )
        v11 = -1;
      v12 = (unsigned __int16 **)operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
      *a2 = v12;
      if ( v12
        || (*a3 = 0, v6 = -2147024882, WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control)
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        for ( i = 1; (v6 & 0x80000000) == 0 && i < *a3; ++i )
        {
          if ( ConvertSidToStringSidW(*(PSID *)&v7[4 * i - 2], &(*a2)[i]) )
          {
            if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                21,
                WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids,
                (*a2)[i]);
            }
          }
          else
          {
            v15 = GetLastError();
            v6 = v15;
            if ( v15 > 0 )
              v6 = (unsigned __int16)v15 | 0x80070000;
            if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids, v6);
            }
          }
        }
      }
      else
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids, v13);
      }
    }
    else
    {
      v16 = GetLastError();
      v6 = v16;
      if ( v16 > 0 )
        v6 = (unsigned __int16)v16 | 0x80070000;
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids, v6);
      }
    }
    GlobalFree(v7);
  }
  return v6;
}

```

## disassembly

```asm
0x18001c988  push    rbx
0x18001c98a  push    rbp
0x18001c98b  push    rsi
0x18001c98c  push    rdi
0x18001c98d  push    r14
0x18001c98f  push    r15
0x18001c991  sub     rsp, 38h
0x18001c995  xor     r9d, r9d; TokenInformationLength
0x18001c998  mov     qword ptr [rdx], 0
0x18001c99f  mov     r14, r8
0x18001c9a2  mov     dword ptr [r8], 0
0x18001c9a9  mov     r15, rdx
0x18001c9ac  mov     [rsp+68h+TokenInformationLength], 0
0x18001c9b4  lea     rax, [rsp+68h+TokenInformationLength]
0x18001c9b9  xor     r8d, r8d; TokenInformation
0x18001c9bc  lea     edx, [r9+2]; TokenInformationClass
0x18001c9c0  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18001c9c5  mov     rdi, rcx
0x18001c9c8  call    cs:__imp_GetTokenInformation
0x18001c9ce  lea     rbp, WPP_GLOBAL_Control
0x18001c9d5  test    eax, eax
0x18001c9d7  jnz     short loc_18001CA36
0x18001c9d9  call    cs:__imp_GetLastError
0x18001c9df  cmp     eax, 7Ah ; 'z'
0x18001c9e2  jnz     short loc_18001CA36
0x18001c9e4  mov     edx, [rsp+68h+TokenInformationLength]; dwBytes
0x18001c9e8  lea     ecx, [rax-3Ah]; uFlags
0x18001c9eb  xor     ebx, ebx
0x18001c9ed  call    cs:__imp_GlobalAlloc
0x18001c9f3  mov     rsi, rax
0x18001c9f6  test    rax, rax
0x18001c9f9  jnz     loc_18001CA7F
0x18001c9ff  mov     ebx, 8007000Eh
0x18001ca04  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca0b  cmp     rcx, rbp
0x18001ca0e  jz      loc_18001CC0E
0x18001ca14  test    byte ptr [rcx+1Ch], 1
0x18001ca18  jz      loc_18001CC0E
0x18001ca1e  mov     rcx, [rcx+10h]
0x18001ca22  lea     edx, [rax+12h]
0x18001ca25  lea     r8, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids
0x18001ca2c  call    WPP_SF_
0x18001ca31  jmp     loc_18001CC0E
0x18001ca36  xor     esi, esi
0x18001ca38  call    cs:__imp_GetLastError
0x18001ca3e  mov     ebx, eax
0x18001ca40  test    eax, eax
0x18001ca42  jle     short loc_18001CA4D
0x18001ca44  movzx   ebx, ax
0x18001ca47  or      ebx, 80070000h
0x18001ca4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca54  cmp     rcx, rbp
0x18001ca57  jz      short loc_18001CA77
0x18001ca59  test    byte ptr [rcx+1Ch], 1
0x18001ca5d  jz      short loc_18001CA77
0x18001ca5f  mov     rcx, [rcx+10h]
0x18001ca63  lea     r8, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids
0x18001ca6a  mov     edx, 13h
0x18001ca6f  mov     r9d, ebx
0x18001ca72  call    WPP_SF_d
0x18001ca77  test    ebx, ebx
0x18001ca79  js      loc_18001CC0E
0x18001ca7f  mov     r9d, [rsp+68h+TokenInformationLength]; TokenInformationLength
0x18001ca84  lea     rax, [rsp+68h+TokenInformationLength]
0x18001ca89  mov     r8, rsi; TokenInformation
0x18001ca8c  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18001ca91  mov     edx, 2; TokenInformationClass
0x18001ca96  mov     rcx, rdi; TokenHandle
0x18001ca99  call    cs:__imp_GetTokenInformation
0x18001ca9f  test    eax, eax
0x18001caa1  jz      loc_18001CBC6
0x18001caa7  mov     eax, [rsi]
0x18001caa9  inc     eax
0x18001caab  mov     ecx, eax
0x18001caad  mov     [r14], eax
0x18001cab0  mov     eax, 8
0x18001cab5  mul     rcx
0x18001cab8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001cabf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001cac6  cmovb   rax, rcx
0x18001caca  mov     rcx, rax; unsigned __int64
0x18001cacd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001cad2  mov     [r15], rax
0x18001cad5  test    rax, rax
0x18001cad8  jnz     short loc_18001CB0C
0x18001cada  mov     [r14], eax
0x18001cadd  mov     ebx, 8007000Eh
0x18001cae2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cae9  cmp     rcx, rbp
0x18001caec  jz      short loc_18001CB0C
0x18001caee  test    byte ptr [rcx+1Ch], 1
0x18001caf2  jz      short loc_18001CB0C
0x18001caf4  mov     rcx, [rcx+10h]
0x18001caf8  lea     edx, [rax+14h]
0x18001cafb  lea     r8, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids
0x18001cb02  call    WPP_SF_
0x18001cb07  jmp     loc_18001CC05
0x18001cb0c  mov     edi, 1
0x18001cb11  jmp     loc_18001CBBC
0x18001cb16  cmp     edi, [r14]
0x18001cb19  jnb     loc_18001CC05
0x18001cb1f  mov     rax, [r15]
0x18001cb22  lea     ecx, [rdi-1]
0x18001cb25  add     rcx, rcx
0x18001cb28  mov     ebp, edi
0x18001cb2a  mov     rcx, [rsi+rcx*8+8]; Sid
0x18001cb2f  lea     rdx, [rax+rbp*8]; StringSid
0x18001cb33  call    cs:__imp_ConvertSidToStringSidW
0x18001cb39  test    eax, eax
0x18001cb3b  jz      short loc_18001CB74
0x18001cb3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb44  lea     rax, WPP_GLOBAL_Control
0x18001cb4b  cmp     rcx, rax
0x18001cb4e  jz      short loc_18001CBBA
0x18001cb50  test    byte ptr [rcx+1Ch], 2
0x18001cb54  jz      short loc_18001CBBA
0x18001cb56  mov     r9, [r15]
0x18001cb59  lea     r8, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids
0x18001cb60  mov     rcx, [rcx+10h]
0x18001cb64  mov     edx, 15h
0x18001cb69  mov     r9, [r9+rbp*8]
0x18001cb6d  call    WPP_SF_S
0x18001cb72  jmp     short loc_18001CBBA
0x18001cb74  call    cs:__imp_GetLastError
0x18001cb7a  mov     ebx, eax
0x18001cb7c  test    eax, eax
0x18001cb7e  jle     short loc_18001CB89
0x18001cb80  movzx   ebx, ax
0x18001cb83  or      ebx, 80070000h
0x18001cb89  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb90  lea     rax, WPP_GLOBAL_Control
0x18001cb97  cmp     rcx, rax
0x18001cb9a  jz      short loc_18001CBBA
0x18001cb9c  test    byte ptr [rcx+1Ch], 1
0x18001cba0  jz      short loc_18001CBBA
0x18001cba2  mov     rcx, [rcx+10h]
0x18001cba6  lea     r8, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids
0x18001cbad  mov     edx, 16h
0x18001cbb2  mov     r9d, ebx
0x18001cbb5  call    WPP_SF_d
0x18001cbba  inc     edi
0x18001cbbc  test    ebx, ebx
0x18001cbbe  jns     loc_18001CB16
0x18001cbc4  jmp     short loc_18001CC05
0x18001cbc6  call    cs:__imp_GetLastError
0x18001cbcc  mov     ebx, eax
0x18001cbce  test    eax, eax
0x18001cbd0  jle     short loc_18001CBDB
0x18001cbd2  movzx   ebx, ax
0x18001cbd5  or      ebx, 80070000h
0x18001cbdb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cbe2  cmp     rcx, rbp
0x18001cbe5  jz      short loc_18001CC05
0x18001cbe7  test    byte ptr [rcx+1Ch], 1
0x18001cbeb  jz      short loc_18001CC05
0x18001cbed  mov     rcx, [rcx+10h]
0x18001cbf1  lea     r8, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids
0x18001cbf8  mov     edx, 17h
0x18001cbfd  mov     r9d, ebx
0x18001cc00  call    WPP_SF_d
0x18001cc05  mov     rcx, rsi; hMem
0x18001cc08  call    cs:__imp_GlobalFree
0x18001cc0e  mov     eax, ebx
0x18001cc10  add     rsp, 38h
0x18001cc14  pop     r15
0x18001cc16  pop     r14
0x18001cc18  pop     rdi
0x18001cc19  pop     rsi
0x18001cc1a  pop     rbp
0x18001cc1b  pop     rbx
0x18001cc1c  retn
```
