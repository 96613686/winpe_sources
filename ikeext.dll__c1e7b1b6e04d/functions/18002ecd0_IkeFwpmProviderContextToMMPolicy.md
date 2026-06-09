# IkeFwpmProviderContextToMMPolicy

- ea: `0x18002ecd0`
- end: `0x18002f006`
- name: `IkeFwpmProviderContextToMMPolicy`
- size: `822`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180035234`

## callees

- `0x180003cf0`
- `0x180008388`
- `0x18002ecd0`
- `0x180050850`
- `0x18005bce4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002edb0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ede9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ee5c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002eea1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002edb0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ede9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ee5c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002eea1`
- `ntdll!EtwEventWriteTransfer` at `0x18002efa5`
- `ntdll!EtwEventWriteTransfer` at `0x18002efa5`

## pseudocode

```c
__int64 __fastcall IkeFwpmProviderContextToMMPolicy(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // r14
  __int64 v6; // r8
  LPCRITICAL_SECTION v7; // rcx
  __int64 v8; // rdi
  unsigned int v9; // ebx
  _QWORD *v10; // r10
  DWORD LockSemaphore; // eax
  LPVOID Value; // rax
  LPVOID v13; // rdx
  __int64 v14; // rsi
  DWORD v15; // eax
  __int64 *v16; // rax
  __int64 v17; // r9
  LPCRITICAL_SECTION v18; // rax
  DWORD v19; // ecx
  __int64 *v20; // rax
  __int64 v21; // rcx
  DWORD v22; // ecx
  char *v23; // rax
  const WCHAR *v24; // rdx
  __int64 v25; // rax
  int v27; // ecx
  unsigned int i; // r8d
  __int64 v29; // rax
  __int64 v31; // [rsp+30h] [rbp-59h] BYREF
  __int64 v32; // [rsp+38h] [rbp-51h] BYREF
  __int64 RecursionCount; // [rsp+40h] [rbp-49h] BYREF
  _DWORD v34[2]; // [rsp+48h] [rbp-41h] BYREF
  __int64 v35; // [rsp+50h] [rbp-39h]
  char *v36; // [rsp+60h] [rbp-29h] BYREF
  int v37; // [rsp+68h] [rbp-21h]
  int v38; // [rsp+6Ch] [rbp-1Dh]
  char *v39; // [rsp+70h] [rbp-19h]
  int v40; // [rsp+78h] [rbp-11h]
  int v41; // [rsp+7Ch] [rbp-Dh]
  __int64 *v42; // [rsp+80h] [rbp-9h]
  __int64 v43; // [rsp+88h] [rbp-1h]
  const WCHAR *v44; // [rsp+90h] [rbp+7h]
  int v45; // [rsp+98h] [rbp+Fh]
  int v46; // [rsp+9Ch] [rbp+13h]
  const char *v47; // [rsp+A0h] [rbp+17h]
  __int64 v48; // [rsp+A8h] [rbp+1Fh]
  __int64 *p_RecursionCount; // [rsp+B0h] [rbp+27h]
  __int64 v50; // [rsp+B8h] [rbp+2Fh]

  v31 = 0;
  v5 = WfpMemAlloc(0x60u, 8u, &v31);
  if ( !v5 )
  {
    v6 = v31;
    *(_QWORD *)(v31 + 64) = a2;
    if ( *(_DWORD *)(a2 + 64) != 5 && *(_DWORD *)(a2 + 64) != 6 && *(_DWORD *)(a2 + 64) != 10 )
      __fastfail(5u);
    *(_QWORD *)v6 = *(_QWORD *)(a2 + 72);
    *a3 = v6;
    v7 = gIkeExtGlobals;
    if ( gIkeExtGlobals[92].RecursionCount )
    {
      v8 = *(_QWORD *)(*(_QWORD *)v6 + 24LL);
      v9 = *(_DWORD *)(*(_QWORD *)v6 + 20LL);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
        if ( LockSemaphore == -1 )
        {
          v13 = 0;
        }
        else
        {
          Value = TlsGetValue(LockSemaphore);
          v7 = gIkeExtGlobals;
          v13 = Value;
          v10 = WPP_GLOBAL_Control;
        }
        v14 = (__int64)v13 + 8;
        if ( !v13 )
          v14 = 0;
        if ( v7
          && (v15 = (DWORD)v7[86].LockSemaphore, v15 != -1)
          && (v16 = (__int64 *)TlsGetValue(v15), v7 = gIkeExtGlobals, v10 = WPP_GLOBAL_Control, v16) )
        {
          v17 = *v16;
        }
        else
        {
          LODWORD(v17) = 0;
        }
        WPP_SF_iSL(
          v10[2],
          11,
          (unsigned int)WPP_610130b6229e37757f1f9736af3100d0_Traceguids,
          v17,
          v14,
          v7[92].RecursionCount);
      }
      if ( (unsigned int)dword_180173278 <= 4 )
        goto LABEL_39;
      v18 = gIkeExtGlobals;
      if ( gIkeExtGlobals )
      {
        v19 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
        if ( v19 != -1 )
        {
          v20 = (__int64 *)TlsGetValue(v19);
          if ( v20 )
          {
            v21 = *v20;
            v18 = gIkeExtGlobals;
LABEL_28:
            v32 = v21;
            v42 = &v32;
            v43 = 8;
            if ( v18 )
            {
              v22 = (DWORD)v18[86].LockSemaphore;
              if ( v22 != -1 )
              {
                v23 = (char *)TlsGetValue(v22);
                v24 = (const WCHAR *)(v23 + 8);
                if ( !v23 )
                  v24 = 0;
                if ( v24 )
                {
                  v25 = -1;
                  while ( v24[++v25] != 0 )
                    ;
                  v27 = 2 * v25 + 2;
                  v18 = gIkeExtGlobals;
                  goto LABEL_38;
                }
                v18 = gIkeExtGlobals;
              }
            }
            v24 = &LocaleName;
            v27 = 2;
LABEL_38:
            v45 = v27;
            v44 = v24;
            v47 = "Overriding IKE policy lifetimes with testIkeSaLifetime";
            v46 = 0;
            v48 = 55;
            RecursionCount = (unsigned int)v18[92].RecursionCount;
            p_RecursionCount = &RecursionCount;
            v34[1] = 4;
            v36 = off_180173280;
            v50 = 8;
            v34[0] = 184549376;
            v35 = 0;
            v37 = *(unsigned __int16 *)off_180173280;
            v39 = byte_180154905;
            v38 = 2;
            v40 = 80;
            v41 = 1;
            LODWORD(v31) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EtwEventWriteTransfer(qword_180173298, v34, 0, 0, 6, &v36);
LABEL_39:
            for ( i = 0; i < v9; *(_DWORD *)(28 * v29 + v8 + 16) = gIkeExtGlobals[92].RecursionCount )
              v29 = i++;
            return IkeReturnError(v5, "IkeFwpmProviderContextToMMPolicy");
          }
          v18 = gIkeExtGlobals;
        }
      }
      v21 = 0;
      goto LABEL_28;
    }
  }
  return IkeReturnError(v5, "IkeFwpmProviderContextToMMPolicy");
}

```

## disassembly

```asm
0x18002ecd0  mov     [rsp-8+arg_8], rbx
0x18002ecd5  mov     [rsp-8+arg_18], rdi
0x18002ecda  push    rbp
0x18002ecdb  push    r14
0x18002ecdd  push    r15
0x18002ecdf  lea     rbp, [rsp-47h]
0x18002ece4  sub     rsp, 0D0h
0x18002eceb  mov     rax, cs:__security_cookie
0x18002ecf2  xor     rax, rsp
0x18002ecf5  mov     [rbp+57h+var_20], rax
0x18002ecf9  mov     rdi, r8
0x18002ecfc  mov     rbx, rdx
0x18002ecff  xor     r15d, r15d
0x18002ed02  lea     r8, [rbp+57h+var_B0]
0x18002ed06  mov     edx, 8; dwFlags
0x18002ed0b  mov     [rbp+57h+var_B0], r15
0x18002ed0f  mov     ecx, 60h ; '`'; dwBytes
0x18002ed14  call    WfpMemAlloc
0x18002ed19  mov     r14, rax
0x18002ed1c  test    rax, rax
0x18002ed1f  jnz     loc_18002EFD2
0x18002ed25  mov     r8, [rbp+57h+var_B0]
0x18002ed29  mov     [r8+40h], rbx
0x18002ed2d  mov     edx, [rbx+40h]
0x18002ed30  sub     edx, 5
0x18002ed33  jz      short loc_18002ED46
0x18002ed35  sub     edx, 1
0x18002ed38  jz      short loc_18002ED46
0x18002ed3a  cmp     edx, 4
0x18002ed3d  jz      short loc_18002ED46
0x18002ed3f  mov     ecx, 5
0x18002ed44  int     29h; Win8: RtlFailFast(ecx)
0x18002ed46  mov     rax, [rbx+48h]
0x18002ed4a  mov     [r8], rax
0x18002ed4d  mov     [rdi], r8
0x18002ed50  mov     rcx, cs:gIkeExtGlobals
0x18002ed57  cmp     [rcx+0E6Ch], r15d
0x18002ed5e  jbe     loc_18002EFD2
0x18002ed64  mov     rax, [r8]
0x18002ed67  mov     rdi, [rax+18h]
0x18002ed6b  mov     ebx, [rax+14h]
0x18002ed6e  mov     r10, cs:WPP_GLOBAL_Control
0x18002ed75  lea     rax, WPP_GLOBAL_Control
0x18002ed7c  cmp     r10, rax
0x18002ed7f  jz      loc_18002EE36
0x18002ed85  cmp     byte ptr [r10+19h], 4
0x18002ed8a  jb      loc_18002EE36
0x18002ed90  test    byte ptr [r10+1Ch], 10h
0x18002ed95  jz      loc_18002EE36
0x18002ed9b  mov     eax, [rcx+0D88h]
0x18002eda1  mov     [rsp+0E0h+arg_0], rsi
0x18002eda9  cmp     eax, 0FFFFFFFFh
0x18002edac  jz      short loc_18002EDC9
0x18002edae  mov     ecx, eax; dwTlsIndex
0x18002edb0  call    cs:__imp_TlsGetValue
0x18002edb6  mov     rcx, cs:gIkeExtGlobals
0x18002edbd  mov     rdx, rax
0x18002edc0  mov     r10, cs:WPP_GLOBAL_Control
0x18002edc7  jmp     short loc_18002EDCC
0x18002edc9  mov     rdx, r15
0x18002edcc  test    rdx, rdx
0x18002edcf  lea     rsi, [rdx+8]
0x18002edd3  cmovz   rsi, r15
0x18002edd7  test    rcx, rcx
0x18002edda  jz      short loc_18002EE07
0x18002eddc  mov     eax, [rcx+0D88h]
0x18002ede2  cmp     eax, 0FFFFFFFFh
0x18002ede5  jz      short loc_18002EE07
0x18002ede7  mov     ecx, eax; dwTlsIndex
0x18002ede9  call    cs:__imp_TlsGetValue
0x18002edef  mov     rcx, cs:gIkeExtGlobals
0x18002edf6  mov     r10, cs:WPP_GLOBAL_Control
0x18002edfd  test    rax, rax
0x18002ee00  jz      short loc_18002EE07
0x18002ee02  mov     r9, [rax]
0x18002ee05  jmp     short loc_18002EE0A
0x18002ee07  mov     r9, r15
0x18002ee0a  mov     eax, [rcx+0E6Ch]
0x18002ee10  lea     r8, WPP_610130b6229e37757f1f9736af3100d0_Traceguids
0x18002ee17  mov     rcx, [r10+10h]
0x18002ee1b  mov     edx, 0Bh
0x18002ee20  mov     dword ptr [rsp+0E0h+var_B8], eax
0x18002ee24  mov     [rsp+0E0h+var_C0], rsi
0x18002ee29  call    WPP_SF_iSL
0x18002ee2e  mov     rsi, [rsp+0E0h+arg_0]
0x18002ee36  mov     eax, cs:dword_180173278
0x18002ee3c  cmp     eax, 4
0x18002ee3f  jbe     loc_18002EFAB
0x18002ee45  mov     rax, cs:gIkeExtGlobals
0x18002ee4c  test    rax, rax
0x18002ee4f  jz      short loc_18002EE7A
0x18002ee51  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002ee57  cmp     ecx, 0FFFFFFFFh
0x18002ee5a  jz      short loc_18002EE7A
0x18002ee5c  call    cs:__imp_TlsGetValue
0x18002ee62  test    rax, rax
0x18002ee65  jz      short loc_18002EE73
0x18002ee67  mov     rcx, [rax]
0x18002ee6a  mov     rax, cs:gIkeExtGlobals
0x18002ee71  jmp     short loc_18002EE7D
0x18002ee73  mov     rax, cs:gIkeExtGlobals
0x18002ee7a  mov     rcx, r15
0x18002ee7d  mov     [rbp+57h+var_A8], rcx
0x18002ee81  lea     rcx, [rbp+57h+var_A8]
0x18002ee85  mov     [rbp+57h+var_60], rcx
0x18002ee89  mov     [rbp+57h+var_58], 8
0x18002ee91  test    rax, rax
0x18002ee94  jz      short loc_18002EEE3
0x18002ee96  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002ee9c  cmp     ecx, 0FFFFFFFFh
0x18002ee9f  jz      short loc_18002EEE3
0x18002eea1  call    cs:__imp_TlsGetValue
0x18002eea7  test    rax, rax
0x18002eeaa  lea     rdx, [rax+8]
0x18002eeae  cmovz   rdx, r15
0x18002eeb2  test    rdx, rdx
0x18002eeb5  jz      short loc_18002EEDC
0x18002eeb7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002eebe  xchg    ax, ax
0x18002eec0  cmp     [rdx+rax*2+2], r15w
0x18002eec6  lea     rax, [rax+1]
0x18002eeca  jnz     short loc_18002EEC0
0x18002eecc  lea     ecx, ds:2[rax*2]
0x18002eed3  mov     rax, cs:gIkeExtGlobals
0x18002eeda  jmp     short loc_18002EEEF
0x18002eedc  mov     rax, cs:gIkeExtGlobals
0x18002eee3  lea     rdx, LocaleName
0x18002eeea  mov     ecx, 2
0x18002eeef  mov     [rbp+57h+var_48], ecx
0x18002eef2  xor     r9d, r9d
0x18002eef5  mov     [rbp+57h+var_50], rdx
0x18002eef9  lea     rcx, aOverridingIkeP; "Overriding IKE policy lifetimes with te"...
0x18002ef00  mov     [rbp+57h+var_40], rcx
0x18002ef04  lea     rdx, [rbp+57h+var_98]
0x18002ef08  mov     [rbp+57h+var_44], r15d
0x18002ef0c  lea     rcx, _TraceLoggingMetadata
0x18002ef13  mov     [rbp+57h+var_38], 37h ; '7'
0x18002ef1b  xor     r8d, r8d
0x18002ef1e  mov     eax, [rax+0E6Ch]
0x18002ef24  mov     [rbp+57h+var_A0], rax
0x18002ef28  lea     rax, [rbp+57h+var_A0]
0x18002ef2c  mov     [rbp+57h+var_30], rax
0x18002ef30  movzx   eax, cs:word_1801548FB
0x18002ef37  mov     [rbp+57h+var_94], eax
0x18002ef3a  mov     rax, cs:off_180173280
0x18002ef41  mov     [rbp+57h+var_80], rax
0x18002ef45  mov     [rbp+57h+var_28], 8
0x18002ef4d  mov     [rbp+57h+var_98], 0B000000h
0x18002ef54  mov     [rbp+57h+var_90], r15
0x18002ef58  movzx   eax, word ptr [rax]
0x18002ef5b  mov     [rbp+57h+var_78], eax
0x18002ef5e  lea     rax, byte_180154905
0x18002ef65  mov     [rbp+57h+var_70], rax
0x18002ef69  lea     rax, _TraceLoggingMetadataEnd
0x18002ef70  sub     eax, ecx
0x18002ef72  mov     [rbp+57h+var_74], 2
0x18002ef79  mov     [rbp+57h+var_68], 50h ; 'P'
0x18002ef80  mov     [rbp+57h+var_64], 1
0x18002ef87  mov     dword ptr [rbp+57h+var_B0], eax
0x18002ef8a  mov     eax, dword ptr [rbp+57h+var_B0]
0x18002ef8d  mov     rcx, cs:qword_180173298
0x18002ef94  lea     rax, [rbp+57h+var_80]
0x18002ef98  mov     [rsp+0E0h+var_B8], rax
0x18002ef9d  mov     dword ptr [rsp+0E0h+var_C0], 6
0x18002efa5  call    cs:__imp_EtwEventWriteTransfer
0x18002efab  mov     r8d, r15d
0x18002efae  test    ebx, ebx
0x18002efb0  jz      short loc_18002EFD2
0x18002efb2  mov     eax, r8d
0x18002efb5  inc     r8d
0x18002efb8  imul    rdx, rax, 1Ch
0x18002efbc  mov     rax, cs:gIkeExtGlobals
0x18002efc3  mov     ecx, [rax+0E6Ch]
0x18002efc9  mov     [rdx+rdi+10h], ecx
0x18002efcd  cmp     r8d, ebx
0x18002efd0  jb      short loc_18002EFB2
0x18002efd2  lea     rdx, aIkefwpmprovide_0; "IkeFwpmProviderContextToMMPolicy"
0x18002efd9  mov     rcx, r14
0x18002efdc  call    IkeReturnError
0x18002efe1  mov     rcx, [rbp+57h+var_20]
0x18002efe5  xor     rcx, rsp; StackCookie
0x18002efe8  call    __security_check_cookie
0x18002efed  lea     r11, [rsp+0E0h+var_10]
0x18002eff5  mov     rbx, [r11+28h]
0x18002eff9  mov     rdi, [r11+38h]
0x18002effd  mov     rsp, r11
0x18002f000  pop     r15
0x18002f002  pop     r14
0x18002f004  pop     rbp
0x18002f005  retn
```
