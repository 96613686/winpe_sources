# PcwpCreateDefaultSecurityDescriptor(utl::unique_ptr<void,ObDereferenceSecurityDescriptorDeleter> *)

- ea: `0x14000e088`
- end: `0x14000e3e0`
- name: `?PcwpCreateDefaultSecurityDescriptor@@YAJPEAV?$unique_ptr@XUObDereferenceSecurityDescriptorDeleter@@@utl@@@Z`
- size: `856`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14000e4e8`

## callees

- `0x140001370`
- `0x14000dcf0`
- `0x14000df74`
- `0x14000e088`
- `0x14000e5ac`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000e31f`
- `ntoskrnl!ExAllocatePool2` at `0x14000e31f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e2aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e2e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e33d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e394`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e3aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e2aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e2e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e33d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e394`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e3aa`
- `ntoskrnl!RtlDeriveCapabilitySidsFromName` at `0x14000e159`
- `ntoskrnl!RtlDeriveCapabilitySidsFromName` at `0x14000e159`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000e174`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000e174`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14000e1a0`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14000e1a0`
- `ntoskrnl!SeExports` at `0x14000e188`
- `ntoskrnl!SeExports` at `0x14000e1b4`
- `ntoskrnl!SeExports` at `0x14000e1ef`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x14000e1cc`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x14000e1cc`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14000e2cd`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14000e2cd`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000e300`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000e300`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14000e35b`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14000e35b`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x14000e381`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x14000e381`

## pseudocode

```c
NTSTATUS __fastcall PcwpCreateDefaultSecurityDescriptor(__int64 a1)
{
  NTSTATUS result; // eax
  int v3; // ebx
  PVOID v4; // rbx
  NTSTATUS v5; // edi
  void *Pool2; // rax
  void *v7; // rdi
  NTSTATUS v8; // esi
  __int64 v9; // rax
  __int64 v10; // [rsp+20h] [rbp-100h]
  __int64 v11; // [rsp+28h] [rbp-F8h]
  ULONG BufferLength; // [rsp+A0h] [rbp-80h] BYREF
  PVOID P; // [rsp+A8h] [rbp-78h] BYREF
  _QWORD v14[2]; // [rsp+B0h] [rbp-70h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+C0h] [rbp-60h] BYREF
  __int64 v16; // [rsp+E0h] [rbp-40h]
  struct _SID_IDENTIFIER_AUTHORITY v17; // [rsp+E8h] [rbp-38h] BYREF
  _BYTE v18[72]; // [rsp+F0h] [rbp-30h] BYREF
  _BYTE v19[72]; // [rsp+138h] [rbp+18h] BYREF
  _BYTE Sid[72]; // [rsp+180h] [rbp+60h] BYREF
  _BYTE v21[72]; // [rsp+1C8h] [rbp+A8h] BYREF

  v14[0] = 3538996;
  v14[1] = L"windowsPerformanceCounters";
  *(_DWORD *)v17.Value = 0;
  *(_WORD *)&v17.Value[4] = 1280;
  P = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v16 = 0;
  BufferLength = 0;
  result = PcwpInitSid(Sid, 0x44u, &v17, 2u, 32, 559);
  if ( result >= 0 )
  {
    LODWORD(v11) = 558;
    LODWORD(v10) = 32;
    result = PcwpInitSid(v19, 0x44u, &v17, 2u, v10, v11);
    if ( result >= 0 )
    {
      result = RtlDeriveCapabilitySidsFromName(v14, v21, v18);
      if ( result >= 0 )
      {
        result = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
        if ( result >= 0 )
        {
          result = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, SeExports->SeAliasAdminsSid, 0);
          if ( result >= 0 )
          {
            if ( RtlSetGroupSecurityDescriptor(SecurityDescriptor, SeExports->SeAliasAdminsSid, 0) >= 0 )
            {
              v3 = PcwpCreateAllowedDacl(&P, 9, SeExports->SeLocalSystemSid);
              if ( v3 >= 0 )
              {
                v4 = P;
                v5 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, (PACL)P, 0);
                if ( v5 >= 0 )
                {
                  BufferLength = RtlLengthSecurityDescriptor(SecurityDescriptor) + 20;
                  Pool2 = (void *)ExAllocatePool2(256, BufferLength, 1417110352);
                  v7 = Pool2;
                  if ( Pool2 )
                  {
                    v8 = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, Pool2, &BufferLength);
                    if ( v8 >= 0 )
                    {
                      v9 = utl::replace<void,ObDereferenceSecurityDescriptorDeleter>(a1);
                      v8 = ObLogSecurityDescriptor(v7, v9, 1);
                    }
                    ExFreePoolWithTag(v7, 0);
                    if ( v4 )
                      ExFreePoolWithTag(v4, 0);
                    return v8;
                  }
                  else
                  {
                    if ( v4 )
                      ExFreePoolWithTag(v4, 0);
                    return -1073741801;
                  }
                }
                else
                {
                  if ( v4 )
                    ExFreePoolWithTag(v4, 0);
                  return v5;
                }
              }
              else
              {
                if ( P )
                  ExFreePoolWithTag(P, 0);
                return v3;
              }
            }
            else
            {
              return 1;
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000e088  mov     [rsp-8+arg_8], rbx
0x14000e08d  mov     [rsp-8+arg_10], rsi
0x14000e092  push    rbp
0x14000e093  push    rdi
0x14000e094  push    r14
0x14000e096  lea     rbp, [rsp-100h]
0x14000e09e  sub     rsp, 220h
0x14000e0a5  mov     rax, cs:__security_cookie
0x14000e0ac  xor     rax, rsp
0x14000e0af  mov     [rbp+110h+var_20], rax
0x14000e0b6  xorps   xmm0, xmm0
0x14000e0b9  mov     dword ptr [rsp+230h+var_208], 22Fh
0x14000e0c1  lea     rax, aWindowsperform; "windowsPerformanceCounters"
0x14000e0c8  mov     [rbp+110h+var_180], 360034h
0x14000e0d0  mov     [rbp+110h+var_178], rax
0x14000e0d4  lea     r8, [rbp+110h+var_148]; struct _SID_IDENTIFIER_AUTHORITY *
0x14000e0d8  xor     eax, eax
0x14000e0da  mov     dword ptr [rbp+110h+var_148.Value], 0
0x14000e0e1  mov     r14, rcx
0x14000e0e4  mov     word ptr [rbp+110h+var_148.Value+4], 500h
0x14000e0ea  lea     rcx, [rbp+110h+Sid]; Sid
0x14000e0ee  mov     [rbp+110h+P], 0
0x14000e0f6  movups  [rbp+110h+SecurityDescriptor], xmm0
0x14000e0fa  lea     esi, [rax+2]
0x14000e0fd  mov     [rbp+110h+var_150], rax
0x14000e101  lea     edi, [rax+44h]
0x14000e104  mov     [rbp+110h+BufferLength], eax
0x14000e107  lea     ebx, [rax+20h]
0x14000e10a  mov     r9d, esi; unsigned __int8
0x14000e10d  mov     edx, edi; unsigned int
0x14000e10f  mov     dword ptr [rsp+230h+var_210], ebx
0x14000e113  movups  [rbp+110h+var_160], xmm0
0x14000e117  call    ?PcwpInitSid@@YAJPEAXKPEAU_SID_IDENTIFIER_AUTHORITY@@EZZ; PcwpInitSid(void *,ulong,_SID_IDENTIFIER_AUTHORITY *,uchar,...)
0x14000e11c  test    eax, eax
0x14000e11e  js      loc_14000E3B8
0x14000e124  mov     dword ptr [rsp+230h+var_208], 22Eh
0x14000e12c  lea     r8, [rbp+110h+var_148]; struct _SID_IDENTIFIER_AUTHORITY *
0x14000e130  mov     r9d, esi; unsigned __int8
0x14000e133  mov     dword ptr [rsp+230h+var_210], ebx
0x14000e137  mov     edx, edi; unsigned int
0x14000e139  lea     rcx, [rbp+110h+var_F8]; Sid
0x14000e13d  call    ?PcwpInitSid@@YAJPEAXKPEAU_SID_IDENTIFIER_AUTHORITY@@EZZ; PcwpInitSid(void *,ulong,_SID_IDENTIFIER_AUTHORITY *,uchar,...)
0x14000e142  test    eax, eax
0x14000e144  js      loc_14000E3B8
0x14000e14a  lea     r8, [rbp+110h+var_140]
0x14000e14e  lea     rdx, [rbp+110h+var_68]
0x14000e155  lea     rcx, [rbp+110h+var_180]
0x14000e159  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x14000e160  nop     dword ptr [rax+rax+00h]
0x14000e165  test    eax, eax
0x14000e167  js      loc_14000E3B8
0x14000e16d  lea     edx, [rbx-1Fh]; Revision
0x14000e170  lea     rcx, [rbp+110h+SecurityDescriptor]; SecurityDescriptor
0x14000e174  call    cs:__imp_RtlCreateSecurityDescriptor
0x14000e17b  nop     dword ptr [rax+rax+00h]
0x14000e180  test    eax, eax
0x14000e182  js      loc_14000E3B8
0x14000e188  mov     rax, cs:__imp_SeExports
0x14000e18f  lea     rcx, [rbp+110h+SecurityDescriptor]; SecurityDescriptor
0x14000e193  xor     r8d, r8d; OwnerDefaulted
0x14000e196  mov     rdx, [rax]
0x14000e199  mov     rdx, [rdx+110h]; Owner
0x14000e1a0  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x14000e1a7  nop     dword ptr [rax+rax+00h]
0x14000e1ac  test    eax, eax
0x14000e1ae  js      loc_14000E3B8
0x14000e1b4  mov     rcx, cs:__imp_SeExports
0x14000e1bb  xor     r8d, r8d; GroupDefaulted
0x14000e1be  mov     rdx, [rcx]
0x14000e1c1  lea     rcx, [rbp+110h+SecurityDescriptor]; SecurityDescriptor
0x14000e1c5  mov     rdx, [rdx+110h]; Group
0x14000e1cc  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x14000e1d3  nop     dword ptr [rax+rax+00h]
0x14000e1d8  test    eax, eax
0x14000e1da  jns     short loc_14000E1E4
0x14000e1dc  lea     eax, [rbx-1Fh]
0x14000e1df  jmp     loc_14000E3B8
0x14000e1e4  mov     ecx, cs:?PcwCounterSetGenericMap@@3U_GENERIC_MAPPING@@A.GenericRead; _GENERIC_MAPPING PcwCounterSetGenericMap ...
0x14000e1ea  mov     edx, 3
0x14000e1ef  mov     rax, cs:__imp_SeExports
0x14000e1f6  mov     r9d, cs:?PcwCounterSetGenericMap@@3U_GENERIC_MAPPING@@A.GenericAll; _GENERIC_MAPPING PcwCounterSetGenericMap ...
0x14000e1fd  mov     [rsp+230h+var_198], esi
0x14000e204  mov     r8, [rax]
0x14000e207  mov     rax, [r8+0C0h]
0x14000e20e  mov     [rsp+230h+var_1A0], rax
0x14000e216  mov     rax, [r8+188h]
0x14000e21d  mov     [rsp+230h+var_1A8], edx
0x14000e224  mov     [rsp+230h+var_1B0], rax
0x14000e22c  mov     rax, [r8+180h]
0x14000e233  mov     [rsp+230h+var_1B8], edx
0x14000e237  mov     [rsp+230h+var_1C0], rax
0x14000e23c  mov     rax, [r8+100h]
0x14000e243  mov     [rsp+230h+var_1C8], ecx
0x14000e247  mov     [rsp+230h+var_1D0], rax
0x14000e24c  lea     rax, [rbp+110h+var_140]
0x14000e250  mov     [rsp+230h+var_1D8], edx
0x14000e254  mov     edx, 9
0x14000e259  mov     [rsp+230h+var_1E0], rax
0x14000e25e  lea     rax, [rbp+110h+var_F8]
0x14000e262  mov     [rsp+230h+var_1E8], ecx
0x14000e266  mov     [rsp+230h+var_1F0], rax
0x14000e26b  lea     rax, [rbp+110h+Sid]
0x14000e26f  mov     [rsp+230h+var_1F8], ecx
0x14000e273  lea     rcx, [rbp+110h+P]
0x14000e277  mov     [rsp+230h+var_200], rax
0x14000e27c  mov     rax, [r8+110h]
0x14000e283  mov     r8, [r8+108h]
0x14000e28a  mov     dword ptr [rsp+230h+var_208], r9d
0x14000e28f  mov     [rsp+230h+var_210], rax
0x14000e294  call    ?PcwpCreateAllowedDacl@@YAJPEAV?$unique_ptr@U_ACL@@U?$default_delete@U_ACL@@@utl@@@utl@@KZZ; PcwpCreateAllowedDacl(utl::unique_ptr<_ACL,utl::default_delete<_ACL>> *,ulong,...)
0x14000e299  mov     ebx, eax
0x14000e29b  test    eax, eax
0x14000e29d  jns     short loc_14000E2BD
0x14000e29f  mov     rcx, [rbp+110h+P]; P
0x14000e2a3  test    rcx, rcx
0x14000e2a6  jz      short loc_14000E2B6
0x14000e2a8  xor     edx, edx; Tag
0x14000e2aa  call    cs:__imp_ExFreePoolWithTag
0x14000e2b1  nop     dword ptr [rax+rax+00h]
0x14000e2b6  mov     eax, ebx
0x14000e2b8  jmp     loc_14000E3B8
0x14000e2bd  mov     rbx, [rbp+110h+P]
0x14000e2c1  lea     rcx, [rbp+110h+SecurityDescriptor]; SecurityDescriptor
0x14000e2c5  mov     r8, rbx; Dacl
0x14000e2c8  xor     r9d, r9d; DaclDefaulted
0x14000e2cb  mov     dl, 1; DaclPresent
0x14000e2cd  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14000e2d4  nop     dword ptr [rax+rax+00h]
0x14000e2d9  mov     edi, eax
0x14000e2db  test    eax, eax
0x14000e2dd  jns     short loc_14000E2FC
0x14000e2df  test    rbx, rbx
0x14000e2e2  jz      short loc_14000E2F5
0x14000e2e4  xor     edx, edx; Tag
0x14000e2e6  mov     rcx, rbx; P
0x14000e2e9  call    cs:__imp_ExFreePoolWithTag
0x14000e2f0  nop     dword ptr [rax+rax+00h]
0x14000e2f5  mov     eax, edi
0x14000e2f7  jmp     loc_14000E3B8
0x14000e2fc  lea     rcx, [rbp+110h+SecurityDescriptor]; SecurityDescriptor
0x14000e300  call    cs:__imp_RtlLengthSecurityDescriptor
0x14000e307  nop     dword ptr [rax+rax+00h]
0x14000e30c  mov     ecx, 100h
0x14000e311  mov     r8d, 54776350h
0x14000e317  add     eax, 14h
0x14000e31a  mov     edx, eax
0x14000e31c  mov     [rbp+110h+BufferLength], eax
0x14000e31f  call    cs:__imp_ExAllocatePool2
0x14000e326  nop     dword ptr [rax+rax+00h]
0x14000e32b  mov     rdi, rax
0x14000e32e  test    rax, rax
0x14000e331  jnz     short loc_14000E350
0x14000e333  test    rbx, rbx
0x14000e336  jz      short loc_14000E349
0x14000e338  xor     edx, edx; Tag
0x14000e33a  mov     rcx, rbx; P
0x14000e33d  call    cs:__imp_ExFreePoolWithTag
0x14000e344  nop     dword ptr [rax+rax+00h]
0x14000e349  mov     eax, 0C0000017h
0x14000e34e  jmp     short loc_14000E3B8
0x14000e350  lea     r8, [rbp+110h+BufferLength]; BufferLength
0x14000e354  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x14000e357  lea     rcx, [rbp+110h+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x14000e35b  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x14000e362  nop     dword ptr [rax+rax+00h]
0x14000e367  mov     esi, eax
0x14000e369  test    eax, eax
0x14000e36b  js      short loc_14000E38F
0x14000e36d  mov     rcx, r14
0x14000e370  call    ??$replace@XUObDereferenceSecurityDescriptorDeleter@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XUObDereferenceSecurityDescriptorDeleter@@@0@@Z; utl::replace<void,ObDereferenceSecurityDescriptorDeleter>(utl::unique_ptr<void,ObDereferenceSecurityDescriptorDeleter> &)
0x14000e375  mov     r8d, 1
0x14000e37b  mov     rdx, rax
0x14000e37e  mov     rcx, rdi
0x14000e381  call    cs:__imp_ObLogSecurityDescriptor
0x14000e388  nop     dword ptr [rax+rax+00h]
0x14000e38d  mov     esi, eax
0x14000e38f  xor     edx, edx; Tag
0x14000e391  mov     rcx, rdi; P
0x14000e394  call    cs:__imp_ExFreePoolWithTag
0x14000e39b  nop     dword ptr [rax+rax+00h]
0x14000e3a0  test    rbx, rbx
0x14000e3a3  jz      short loc_14000E3B6
0x14000e3a5  xor     edx, edx; Tag
0x14000e3a7  mov     rcx, rbx; P
0x14000e3aa  call    cs:__imp_ExFreePoolWithTag
0x14000e3b1  nop     dword ptr [rax+rax+00h]
0x14000e3b6  mov     eax, esi
0x14000e3b8  mov     rcx, [rbp+110h+var_20]
0x14000e3bf  xor     rcx, rsp; StackCookie
0x14000e3c2  call    __security_check_cookie
0x14000e3c7  lea     r11, [rsp+230h+var_10]
0x14000e3cf  mov     rbx, [r11+28h]
0x14000e3d3  mov     rsi, [r11+30h]
0x14000e3d7  mov     rsp, r11
0x14000e3da  pop     r14
0x14000e3dc  pop     rdi
0x14000e3dd  pop     rbp
0x14000e3de  retn
```
