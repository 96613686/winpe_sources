# UpdateNlsInfoCache

- ea: `0x180029ec0`
- end: `0x18002a550`
- name: `UpdateNlsInfoCache`
- size: `1680`
- prototype: ``
- caller_count: `9`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001cd50`
- `0x180022a60`
- `0x180023c10`
- `0x180024ed0`
- `0x180027400`
- `0x180028630`
- `0x180029660`
- `0x180046ac0`
- `0x180048f20`

## callees

- `0x18001cd34`
- `0x180024c80`
- `0x1800265f0`
- `0x180028360`
- `0x180028490`
- `0x1800285f0`
- `0x180029ec0`
- `0x18002aabc`
- `0x18002b12c`
- `0x1800486a0`
- `0x18004a310`
- `0x18004b408`
- `0x18012c3ac`
- `0x1801369c9`
- `0x180142ba0`
- `0x180194eb9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002a459`
- `ntdll!RtlInitUnicodeString` at `0x18002a459`
- `ntdll!NtOpenKey` at `0x18002a4a5`
- `ntdll!NtOpenKey` at `0x18002a4a5`
- `ntdll!NtCreateKey` at `0x18002a4dd`
- `ntdll!NtCreateKey` at `0x18002a4dd`
- `ntdll!RtlOpenCurrentUser` at `0x18002a2b1`
- `ntdll!RtlOpenCurrentUser` at `0x18002a2b1`
- `ntdll!CsrClientCallServer` at `0x18002a205`
- `ntdll!CsrClientCallServer` at `0x18002a205`
- `ntdll!CsrCaptureMessageBuffer` at `0x18002a1df`
- `ntdll!CsrCaptureMessageBuffer` at `0x18002a1df`
- `ntdll!CsrFreeCaptureBuffer` at `0x18002a22d`
- `ntdll!CsrFreeCaptureBuffer` at `0x18002a22d`
- `ntdll!CsrAllocateCaptureBuffer` at `0x180029f6f`
- `ntdll!CsrAllocateCaptureBuffer` at `0x180029f6f`
- `ntdll!NtClose` at `0x180029ff9`
- `ntdll!NtClose` at `0x18002a34f`
- `ntdll!NtClose` at `0x18002a4f5`
- `ntdll!NtClose` at `0x18002a533`
- `ntdll!NtClose` at `0x180029ff9`
- `ntdll!NtClose` at `0x18002a34f`
- `ntdll!NtClose` at `0x18002a4f5`
- `ntdll!NtClose` at `0x18002a533`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180029efc`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002a06d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180029efc`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002a06d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002a159`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002a1a8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002a159`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002a1a8`

## pseudocode

```c
signed __int16 __fastcall UpdateNlsInfoCache(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // r14d
  bool v5; // zf
  struct _CSR_CAPTURE_BUFFER *CaptureBuffer; // rax
  struct _CSR_CAPTURE_BUFFER *v7; // rsi
  NTSTATUS v8; // edi
  HANDLE v9; // rdi
  __int64 v10; // rdi
  __int64 v11; // rax
  DWORD v12; // edi
  __int64 i; // rdx
  unsigned int *WindowsLocaleData; // rax
  __int64 v15; // r8
  DWORD v16; // edi
  _WORD *v17; // rcx
  __int64 NamedLocaleHashNode; // rax
  signed __int16 result; // ax
  int GlobalizationUserModelType; // eax
  int v21; // eax
  __int64 v22; // rcx
  WCHAR *v23; // rax
  __int64 v24; // r8
  const WCHAR *v25; // rdx
  WCHAR *v26; // r9
  __int64 v27; // rcx
  WCHAR *v28; // rcx
  __int64 v29; // rdx
  int v30; // eax
  NTSTATUS v31; // edi
  HANDLE v32; // rcx
  void *v33; // rdi
  HANDLE Handle; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  ULONG Disposition; // [rsp+50h] [rbp-B0h] BYREF
  int v37; // [rsp+54h] [rbp-ACh] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  WCHAR ApiMessage[32]; // [rsp+A0h] [rbp-60h] BYREF
  PVOID CapturedData; // [rsp+E0h] [rbp-20h] BYREF
  int v42; // [rsp+E8h] [rbp-18h]

  v3 = a2;
  if ( *(_WORD *)(a1 + 1684) != 3 )
    RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
  if ( *(_WORD *)(a1 + 1684) == 3 || *(_WORD *)(a1 + 1686) )
  {
    v5 = *(_WORD *)(a1 + 1684) == 1;
    *(_WORD *)(a1 + 1686) = 2;
    if ( v5 )
    {
      memset_0(ApiMessage, 0, 0x3B8u);
      CaptureBuffer = CsrAllocateCaptureBuffer(1u, 0x67Cu);
      v7 = CaptureBuffer;
      if ( CaptureBuffer )
      {
        CsrCaptureMessageBuffer(CaptureBuffer, 0, 0x67Cu, &CapturedData);
        v42 = 1660;
        v8 = CsrClientCallServer(ApiMessage, v7, (CSR_API_NUMBER)0x1001B, 0x10u);
        if ( v8 >= 0 )
          memcpy_0((void *)(a1 + 24), CapturedData, 0x67Cu);
        CsrFreeCaptureBuffer(v7);
      }
      else
      {
        v8 = -1073741801;
      }
      if ( *(_WORD *)(a1 + 1684) == 1 && v8 >= 0 )
      {
LABEL_14:
        if ( *(_WORD *)(a1 + 24) == 0xFFFF )
        {
          *(_QWORD *)(a1 + 16) = 0;
        }
        else
        {
          v10 = gpOneCustomHashNode;
          _InterlockedExchange64((volatile __int64 *)(a1 + 16), GetNamedLocaleHashNode(a1 + 26, 0));
          if ( !v10 && gpOneCustomHashNode )
            gpOneCustomHashNode = 0;
        }
        if ( *(_QWORD *)(a1 + 16) )
        {
LABEL_37:
          result = _InterlockedCompareExchange16((volatile signed __int16 *)(a1 + 1686), 0, 2);
          if ( *(_WORD *)(a1 + 1684) == 3 )
            return result;
          return RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
        }
        v11 = gpSysLocHashN;
        if ( gpSysLocHashN || BasepIsSecureProcess )
        {
LABEL_36:
          *(_QWORD *)(a1 + 16) = v11;
          goto LABEL_37;
        }
        RtlAcquireSRWLockExclusive(&gTblPtrsLock);
        if ( gpSysLocHashN )
          goto LABEL_35;
        v12 = gSystemLocale;
        for ( i = *((_QWORD *)P
                  + (((unsigned __int8)gSystemLocale
                    ^ (unsigned __int8)((gSystemLocale ^ ((unsigned __int64)gSystemLocale >> 7)) >> 7))
                   & 0x7F)); i; i = *(_QWORD *)(i + 88) )
        {
          if ( *(_DWORD *)i == gSystemLocale )
            break;
        }
        gpSysLocHashN = i;
        if ( i )
          goto LABEL_35;
        if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
          goto LABEL_69;
        WindowsLocaleData = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
        if ( WindowsLocaleData )
        {
          if ( (_WORD)v12 != 127 )
          {
            v16 = HIWORD(v12);
            if ( (v16 & 0xF) == 0 )
            {
              v17 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *WindowsLocaleData);
LABEL_31:
              NamedLocaleHashNode = MakeNamedLocaleHashNode(v17, 0);
              goto LABEL_32;
            }
            v29 = WindowsLocaleData[54];
            v17 = (_WORD *)qword_1803A6BD0;
            if ( (_DWORD)v29 )
              v17 = (_WORD *)(qword_1803A6BD0
                            + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v29 + 2LL * (v16 & 0xF)) - 2)
                            + 2);
            if ( v17 && *v17 )
              goto LABEL_31;
LABEL_69:
            gpSysLocHashN = 0;
LABEL_33:
            gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
            if ( !gpSysLocHashN )
              gpSysLocHashN = gpInvLocHashN;
            goto LABEL_35;
          }
          NamedLocaleHashNode = MakeLocHashNodeFromSystemLocale(WindowsLocaleData, v12, v15, 0);
        }
        else
        {
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
            goto LABEL_69;
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
            || (unsigned int)CreateTransientLocales() )
          {
            NamedLocaleHashNode = FindLocaleHashNode(v12);
          }
          else
          {
            NamedLocaleHashNode = 0;
          }
        }
LABEL_32:
        gpSysLocHashN = NamedLocaleHashNode;
        if ( !NamedLocaleHashNode )
          goto LABEL_33;
LABEL_35:
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        v11 = gpSysLocHashN;
        goto LABEL_36;
      }
    }
    Handle = 0;
    if ( (HANDLE *)a1 != &gNlsProcessLocalCache )
    {
      OpenRegistryInternationalKey(&Handle, 0x20019u);
      goto LABEL_11;
    }
    if ( gNlsProcessLocalCache )
    {
      Handle = gNlsProcessLocalCache;
LABEL_11:
      v9 = Handle;
      NlsUpdateCacheInfo(a1 + 24, Handle, v3);
      if ( *(_WORD *)(a1 + 1684) == 3 && v9 )
        NtClose(v9);
      goto LABEL_14;
    }
    KeyHandle = 0;
    Disposition = 0;
    memset(&ObjectAttributes, 0, 44);
    DestinationString = 0;
    GlobalizationUserModelType = GetGlobalizationUserModelType(0, a2, a3);
    if ( GlobalizationUserModelType == 1 )
    {
      v21 = RtlOpenCurrentUser(0x2000000u, &KeyHandle);
    }
    else
    {
      v30 = GlobalizationUserModelType - 2;
      if ( v30 )
      {
        if ( v30 != 1 )
        {
LABEL_64:
          SetLastError_0(0x3F1u);
          goto LABEL_11;
        }
        v37 = 0;
        v21 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, &KeyHandle, &v37);
      }
      else
      {
        v21 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, &KeyHandle);
      }
    }
    if ( v21 >= 0 )
    {
      ApiMessage[0] = 0;
      v22 = 512;
      v23 = ApiMessage;
      do
      {
        if ( !*v23 )
          break;
        ++v23;
        --v22;
      }
      while ( v22 );
      if ( !v22 )
        goto LABEL_62;
      v24 = v22;
      v25 = L"Control Panel\\International";
      v26 = &ApiMessage[512 - v22];
      v27 = 2147483646;
      do
      {
        if ( !v27 )
          break;
        if ( !*v25 )
          break;
        *v26++ = *v25++;
        --v27;
        --v24;
      }
      while ( v24 );
      v28 = v26 - 1;
      if ( v24 )
        v28 = v26;
      *v28 = 0;
      if ( v24 )
      {
        RtlInitUnicodeString(&DestinationString, ApiMessage);
        ObjectAttributes.RootDirectory = KeyHandle;
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        Disposition = 0;
        v31 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
        if ( v31 < 0 )
          v31 = NtCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
        if ( KeyHandle )
          NtClose(KeyHandle);
        if ( v31 >= 0 )
        {
          v32 = Handle;
        }
        else
        {
          v32 = 0;
          Handle = 0;
        }
        if ( v31 >= 0 )
        {
          v33 = (void *)_InterlockedCompareExchange64(
                          (volatile signed __int64 *)&gNlsProcessLocalCache,
                          (signed __int64)v32,
                          0);
          if ( v33 )
          {
            if ( Handle )
              NtClose(Handle);
            Handle = v33;
          }
          goto LABEL_11;
        }
      }
      else
      {
LABEL_62:
        if ( KeyHandle )
          NtClose(KeyHandle);
      }
    }
    goto LABEL_64;
  }
  return RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
}

```

## disassembly

```asm
0x180029ec0  push    rbp
0x180029ec2  push    rbx
0x180029ec3  push    r14
0x180029ec5  lea     rbp, [rsp-3C0h]
0x180029ecd  sub     rsp, 4C0h
0x180029ed4  mov     rax, cs:__security_cookie
0x180029edb  xor     rax, rsp
0x180029ede  mov     [rbp+3D0h+var_30], rax
0x180029ee5  cmp     word ptr [rcx+694h], 3
0x180029eed  mov     r14d, edx
0x180029ef0  mov     rbx, rcx
0x180029ef3  jz      short loc_180029F08
0x180029ef5  lea     rcx, gNlsProcessCacheLock
0x180029efc  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180029f03  nop     dword ptr [rax+rax+00h]
0x180029f08  cmp     word ptr [rbx+694h], 3
0x180029f10  jnz     loc_18002A24B
0x180029f16  mov     [rsp+4D0h+arg_10], rdi
0x180029f1e  mov     [rsp+4D0h+var_18], r12
0x180029f26  mov     r12d, 2
0x180029f2c  mov     [rsp+4D0h+var_20], r15
0x180029f34  xor     r15d, r15d
0x180029f37  cmp     word ptr [rbx+694h], 1
0x180029f3f  mov     edi, r15d
0x180029f42  mov     [rbx+696h], r12w
0x180029f4a  jnz     short loc_180029FA2
0x180029f4c  xor     edx, edx; Val
0x180029f4e  mov     [rsp+4D0h+arg_8], rsi
0x180029f56  mov     r8d, 3B8h; Size
0x180029f5c  lea     rcx, [rbp+3D0h+ApiMessage]; void *
0x180029f60  call    memset_0
0x180029f65  mov     edx, 67Ch; BufferSize
0x180029f6a  mov     ecx, 1; ArgumentCount
0x180029f6f  call    cs:__imp_CsrAllocateCaptureBuffer
0x180029f76  nop     dword ptr [rax+rax+00h]
0x180029f7b  mov     rsi, rax
0x180029f7e  test    rax, rax
0x180029f81  jnz     loc_18002A1D0
0x180029f87  mov     edi, 0C0000017h
0x180029f8c  cmp     word ptr [rbx+694h], 1
0x180029f94  mov     rsi, [rsp+4D0h+arg_8]
0x180029f9c  jz      loc_18002A23E
0x180029fa2  lea     rax, gNlsProcessLocalCache
0x180029fa9  mov     [rsp+4D0h+Handle], r15
0x180029fae  cmp     rbx, rax
0x180029fb1  jnz     loc_18002A43D
0x180029fb7  mov     rax, cs:gNlsProcessLocalCache
0x180029fbe  test    rax, rax
0x180029fc1  jz      loc_18002A269
0x180029fc7  mov     rax, cs:gNlsProcessLocalCache
0x180029fce  mov     [rsp+4D0h+Handle], rax
0x180029fd3  mov     rdi, [rsp+4D0h+Handle]
0x180029fd8  lea     rcx, [rbx+18h]
0x180029fdc  mov     rdx, rdi
0x180029fdf  mov     r8d, r14d
0x180029fe2  call    NlsUpdateCacheInfo
0x180029fe7  cmp     word ptr [rbx+694h], 3
0x180029fef  jnz     short loc_18002A005
0x180029ff1  test    rdi, rdi
0x180029ff4  jz      short loc_18002A005
0x180029ff6  mov     rcx, rdi; Handle
0x180029ff9  call    cs:__imp_NtClose
0x18002a000  nop     dword ptr [rax+rax+00h]
0x18002a005  mov     eax, 0FFFFh
0x18002a00a  cmp     [rbx+18h], ax
0x18002a00e  jz      loc_18002A260
0x18002a014  mov     rdi, cs:gpOneCustomHashNode
0x18002a01b  lea     rcx, [rbx+1Ah]
0x18002a01f  xor     edx, edx
0x18002a021  call    GetNamedLocaleHashNode
0x18002a026  xchg    rax, [rbx+10h]
0x18002a02a  test    rdi, rdi
0x18002a02d  jnz     short loc_18002A03F
0x18002a02f  cmp     cs:gpOneCustomHashNode, r15
0x18002a036  jz      short loc_18002A03F
0x18002a038  mov     cs:gpOneCustomHashNode, r15
0x18002a03f  cmp     [rbx+10h], r15
0x18002a043  jnz     loc_18002A170
0x18002a049  mov     rax, cs:gpSysLocHashN
0x18002a050  test    rax, rax
0x18002a053  jnz     loc_18002A16C
0x18002a059  cmp     cs:BasepIsSecureProcess, r15b
0x18002a060  jnz     loc_18002A16C
0x18002a066  lea     rcx, gTblPtrsLock
0x18002a06d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002a074  nop     dword ptr [rax+rax+00h]
0x18002a079  cmp     cs:gpSysLocHashN, r15
0x18002a080  jnz     loc_18002A152
0x18002a086  mov     edi, cs:gSystemLocale
0x18002a08c  mov     rax, cs:P
0x18002a093  mov     ecx, edi
0x18002a095  shr     rcx, 7
0x18002a099  xor     rcx, rdi
0x18002a09c  shr     rcx, 7
0x18002a0a0  xor     rcx, rdi
0x18002a0a3  and     ecx, 7Fh
0x18002a0a6  mov     rdx, [rax+rcx*8]
0x18002a0aa  test    rdx, rdx
0x18002a0ad  jz      short loc_18002A0B7
0x18002a0af  cmp     [rdx], edi
0x18002a0b1  jnz     loc_18002A3A8
0x18002a0b7  mov     cs:gpSysLocHashN, rdx
0x18002a0be  test    rdx, rdx
0x18002a0c1  jnz     loc_18002A152
0x18002a0c7  test    edi, 0FFF00000h
0x18002a0cd  jnz     loc_18002A39C
0x18002a0d3  cmp     cs:BasepIsSecureProcess, r15b
0x18002a0da  jnz     loc_18002A39C
0x18002a0e0  mov     ecx, edi
0x18002a0e2  call    GetWindowsLocaleData
0x18002a0e7  test    rax, rax
0x18002a0ea  jz      loc_18002A3BA
0x18002a0f0  cmp     di, 7Fh
0x18002a0f4  jz      loc_18002A3DD
0x18002a0fa  shr     edi, 10h
0x18002a0fd  test    dil, 0Fh
0x18002a101  jnz     loc_18002A36A
0x18002a107  mov     ecx, [rax]
0x18002a109  mov     rax, cs:qword_1803A6BD0
0x18002a110  add     rax, r12
0x18002a113  lea     rcx, [rax+rcx*2]
0x18002a117  xor     edx, edx
0x18002a119  call    MakeNamedLocaleHashNode
0x18002a11e  mov     cs:gpSysLocHashN, rax
0x18002a125  test    rax, rax
0x18002a128  jnz     short loc_18002A152
0x18002a12a  xor     edx, edx
0x18002a12c  lea     rcx, aEnUs; "en-US"
0x18002a133  call    MakeNamedLocaleHashNode
0x18002a138  mov     cs:gpSysLocHashN, rax
0x18002a13f  test    rax, rax
0x18002a142  jnz     short loc_18002A152
0x18002a144  mov     rdx, cs:gpInvLocHashN
0x18002a14b  mov     cs:gpSysLocHashN, rdx
0x18002a152  lea     rcx, gTblPtrsLock
0x18002a159  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002a160  nop     dword ptr [rax+rax+00h]
0x18002a165  mov     rax, cs:gpSysLocHashN
0x18002a16c  mov     [rbx+10h], rax
0x18002a170  mov     eax, r12d
0x18002a173  mov     edx, r15d
0x18002a176  lock cmpxchg [rbx+696h], dx
0x18002a17f  cmp     word ptr [rbx+694h], 3
0x18002a187  mov     r15, [rsp+4D0h+var_20]
0x18002a18f  mov     r12, [rsp+4D0h+var_18]
0x18002a197  mov     rdi, [rsp+4D0h+arg_10]
0x18002a19f  jz      short loc_18002A1B4
0x18002a1a1  lea     rcx, gNlsProcessCacheLock
0x18002a1a8  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002a1af  nop     dword ptr [rax+rax+00h]
0x18002a1b4  mov     rcx, [rbp+3D0h+var_30]
0x18002a1bb  xor     rcx, rsp; StackCookie
0x18002a1be  call    __security_check_cookie
0x18002a1c3  add     rsp, 4C0h
0x18002a1ca  pop     r14
0x18002a1cc  pop     rbx
0x18002a1cd  pop     rbp
0x18002a1ce  retn
0x18002a1d0  lea     r9, [rbp+3D0h+CapturedData]; CapturedData
0x18002a1d4  xor     edx, edx; MessageBuffer
0x18002a1d6  mov     r8d, 67Ch; MessageLength
0x18002a1dc  mov     rcx, rsi; CaptureBuffer
0x18002a1df  call    cs:__imp_CsrCaptureMessageBuffer
0x18002a1e6  nop     dword ptr [rax+rax+00h]
0x18002a1eb  mov     r9d, 10h; DataLength
0x18002a1f1  mov     [rbp+3D0h+var_3E8], 67Ch
0x18002a1f8  mov     r8d, 1001Bh; ApiNumber
0x18002a1fe  lea     rcx, [rbp+3D0h+ApiMessage]; ApiMessage
0x18002a202  mov     rdx, rsi; CaptureBuffer
0x18002a205  call    cs:__imp_CsrClientCallServer
0x18002a20c  nop     dword ptr [rax+rax+00h]
0x18002a211  mov     edi, eax
0x18002a213  test    eax, eax
0x18002a215  js      short loc_18002A22A
0x18002a217  mov     rdx, [rbp+3D0h+CapturedData]; Src
0x18002a21b  lea     rcx, [rbx+18h]; void *
0x18002a21f  mov     r8d, 67Ch; Size
0x18002a225  call    memcpy_0
0x18002a22a  mov     rcx, rsi; CaptureBuffer
0x18002a22d  call    cs:__imp_CsrFreeCaptureBuffer
0x18002a234  nop     dword ptr [rax+rax+00h]
0x18002a239  jmp     loc_180029F8C
0x18002a23e  test    edi, edi
0x18002a240  jns     loc_18002A005
0x18002a246  jmp     loc_180029FA2
0x18002a24b  movzx   eax, word ptr [rbx+696h]
0x18002a252  test    ax, ax
0x18002a255  jnz     loc_180029F16
0x18002a25b  jmp     loc_18002A1A1
0x18002a260  mov     [rbx+10h], r15
0x18002a264  jmp     loc_18002A03F
0x18002a269  mov     rcx, [rsp+4D0h+Handle]
0x18002a26e  test    rcx, rcx
0x18002a271  jnz     loc_18002A515
0x18002a277  xorps   xmm0, xmm0
0x18002a27a  mov     [rsp+4D0h+KeyHandle], r15
0x18002a27f  movups  xmmword ptr [rsp+4D0h+ObjectAttributes.ObjectName], xmm0
0x18002a284  xor     eax, eax
0x18002a286  mov     [rsp+4D0h+var_480], r15d
0x18002a28b  movups  xmmword ptr [rsp+4D0h+ObjectAttributes+1Ch], xmm0
0x18002a290  movups  xmmword ptr [rsp+4D0h+ObjectAttributes.Length], xmm0
0x18002a295  movups  xmmword ptr [rbp+3D0h+DestinationString.Length], xmm0
0x18002a299  call    GetGlobalizationUserModelType
0x18002a29e  cmp     eax, 1
0x18002a2a1  jnz     loc_18002A3EF
0x18002a2a7  lea     rdx, [rsp+4D0h+KeyHandle]; KeyHandle
0x18002a2ac  mov     ecx, 2000000h; DesiredAccess
0x18002a2b1  call    cs:__imp_RtlOpenCurrentUser
0x18002a2b8  nop     dword ptr [rax+rax+00h]
0x18002a2bd  test    eax, eax
0x18002a2bf  js      loc_18002A35B
0x18002a2c5  mov     r8d, 200h
0x18002a2cb  mov     [rbp+3D0h+ApiMessage], r15w
0x18002a2d0  mov     ecx, r8d
0x18002a2d3  lea     rax, [rbp+3D0h+ApiMessage]
0x18002a2d7  cmp     [rax], r15w
0x18002a2db  jz      short loc_18002A2E6
0x18002a2dd  add     rax, r12
0x18002a2e0  sub     rcx, 1
0x18002a2e4  jnz     short loc_18002A2D7
0x18002a2e6  mov     r9, r8
0x18002a2e9  sub     r9, rcx
0x18002a2ec  test    rcx, rcx
0x18002a2ef  cmovz   r9, r15
0x18002a2f3  jz      short loc_18002A345
0x18002a2f5  sub     r8, r9
0x18002a2f8  lea     rdx, aControlPanelIn; "Control Panel\\International"
0x18002a2ff  lea     r9, [rbp+r9*2+3D0h+ApiMessage]
0x18002a304  mov     ecx, 7FFFFFFEh
0x18002a309  jz      short loc_18002A330
0x18002a30b  nop     dword ptr [rax+rax+00h]
0x18002a310  test    rcx, rcx
0x18002a313  jz      short loc_18002A330
0x18002a315  movzx   eax, word ptr [rdx]
0x18002a318  test    ax, ax
0x18002a31b  jz      short loc_18002A330
0x18002a31d  mov     [r9], ax
0x18002a321  add     rdx, r12
0x18002a324  add     r9, r12
0x18002a327  dec     rcx
0x18002a32a  sub     r8, 1
0x18002a32e  jnz     short loc_18002A310
0x18002a330  test    r8, r8
0x18002a333  lea     rcx, [r9-2]
0x18002a337  cmovnz  rcx, r9
0x18002a33b  mov     [rcx], r15w
0x18002a33f  jnz     loc_18002A451
0x18002a345  mov     rcx, [rsp+4D0h+KeyHandle]; Handle
0x18002a34a  test    rcx, rcx
0x18002a34d  jz      short loc_18002A35B
0x18002a34f  call    cs:__imp_NtClose
0x18002a356  nop     dword ptr [rax+rax+00h]
0x18002a35b  mov     ecx, 3F1h; dwErrCode
0x18002a360  call    SetLastError_0
0x18002a365  jmp     loc_180029FD3
0x18002a36a  mov     edx, [rax+0D8h]
0x18002a370  mov     rcx, cs:qword_1803A6BD0
0x18002a377  test    edx, edx
0x18002a379  jz      short loc_18002A38D
0x18002a37b  and     edi, 0Fh
0x18002a37e  lea     rdx, [rdx+rdi*2]
0x18002a382  mov     eax, [rcx+rdx*2-2]
0x18002a386  lea     rcx, [rcx+rax*2]
0x18002a38a  add     rcx, r12
0x18002a38d  test    rcx, rcx
0x18002a390  jz      short loc_18002A39C
0x18002a392  cmp     [rcx], r15w
0x18002a396  jnz     loc_18002A117
0x18002a39c  mov     cs:gpSysLocHashN, r15
0x18002a3a3  jmp     loc_18002A12A
0x18002a3a8  mov     rdx, [rdx+58h]
0x18002a3ac  test    rdx, rdx
0x18002a3af  jnz     loc_18002A0AF
0x18002a3b5  jmp     loc_18002A0B7
0x18002a3ba  call    Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline
0x18002a3bf  test    eax, eax
0x18002a3c1  jnz     short loc_18002A39C
0x18002a3c3  call    Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline
0x18002a3c8  test    eax, eax
0x18002a3ca  jnz     short loc_18002A408
0x18002a3cc  call    CreateTransientLocales
0x18002a3d1  test    eax, eax
0x18002a3d3  jnz     short loc_18002A408
0x18002a3d5  mov     rax, r15
0x18002a3d8  jmp     loc_18002A11E
0x18002a3dd  xor     r9d, r9d
0x18002a3e0  mov     edx, edi
0x18002a3e2  mov     rcx, rax
0x18002a3e5  call    MakeLocHashNodeFromSystemLocale
0x18002a3ea  jmp     loc_18002A11E
0x18002a3ef  sub     eax, r12d
0x18002a3f2  jnz     short loc_18002A414
0x18002a3f4  lea     rdx, [rsp+4D0h+KeyHandle]; KeyHandle
0x18002a3f9  mov     ecx, 2000000h; DesiredAccess
0x18002a3fe  call    OpenGlobalizationUserSettingsKey_ForSingleUserModel
0x18002a403  jmp     loc_18002A2BD
0x18002a408  mov     ecx, edi
0x18002a40a  call    FindLocaleHashNode
0x18002a40f  jmp     loc_18002A11E
0x18002a414  cmp     eax, 1
  ... truncated ...
```
