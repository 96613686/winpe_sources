# AlpcPort::CreateServerPort(_GUID const &,SIPC_SERVICE_BOUNDARY,void *,SipcPort * *)

- ea: `0x18007812c`
- end: `0x18007833b`
- name: `?CreateServerPort@AlpcPort@@SAJAEBU_GUID@@W4SIPC_SERVICE_BOUNDARY@@PEAXPEAPEAVSipcPort@@@Z`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005d190`

## callees

- `0x18007812c`
- `0x180078344`
- `0x1800a3a00`
- `0x1800a9da4`
- `0x1800abe04`
- `0x1800f0990`
- `0x1800f2448`
- `0x180141a70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007821a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007821a`
- `ntdll!NtAlpcCreatePort` at `0x180078272`
- `ntdll!NtAlpcCreatePort` at `0x180078272`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180078210`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180078210`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078244`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078296`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800782c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800782ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078244`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078296`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800782c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800782ea`

## pseudocode

```c
__int64 __fastcall AlpcPort::CreateServerPort(__int64 a1, __int64 a2, __int64 a3, AlpcPort **a4)
{
  AlpcPort *v5; // rax
  SipcPort *v6; // rax
  AlpcPort *v7; // rsi
  int v8; // ebx
  signed int LastError; // eax
  int v10; // eax
  PSECURITY_DESCRIPTOR v11; // rcx
  unsigned int v12; // edi
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+20h] [rbp-E0h] BYREF
  SipcPort *v15; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v16; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE *v17; // [rsp+40h] [rbp-C0h]
  __int64 v18; // [rsp+48h] [rbp-B8h]
  PSECURITY_DESCRIPTOR v19; // [rsp+50h] [rbp-B0h]
  const struct _SECURITY_QUALITY_OF_SERVICE *v20; // [rsp+58h] [rbp-A8h]
  _BYTE v21[192]; // [rsp+60h] [rbp-A0h] BYREF

  *a4 = 0;
  v5 = (AlpcPort *)operator new(0x1F8u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v5 )
  {
    v15 = 0;
    goto LABEL_23;
  }
  v6 = AlpcPort::AlpcPort(v5, 0);
  v15 = v6;
  v7 = v6;
  if ( !v6 )
  {
LABEL_23:
    v8 = -2147024882;
    goto LABEL_24;
  }
  v8 = SipcPort::Initialize(v6);
  if ( v8 < 0 )
  {
LABEL_24:
    utl::unique_ptr<AlpcPort,utl::default_delete<AlpcPort>>::~unique_ptr<AlpcPort,utl::default_delete<AlpcPort>>(&v15);
    return (unsigned int)v8;
  }
  AlpcPortString::AlpcPortString(v21, &xmmword_1801F17C8, 1);
  v18 = 0;
  v20 = &AlpcPort::c_anonymousSecurityQos;
  v17 = v21;
  v16 = *(_OWORD *)&AlpcPort::c_serverObjectAttributes.Length;
  v19 = 0;
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GA;;;WD)(A;;0x001F0001;;;AC)(A;;0x001F0001;;;SY)(A;;0x00020001;;;BA)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = -2147418113;
    if ( LastError < 0 )
      v8 = LastError;
    if ( SecurityDescriptor )
    {
      LocalFree(SecurityDescriptor);
      SecurityDescriptor = 0;
    }
    goto LABEL_24;
  }
  v19 = SecurityDescriptor;
  v10 = NtAlpcCreatePort((char *)v7 + 48, &v16, &AlpcPort::c_serverPortAlpcAttributes);
  v11 = SecurityDescriptor;
  if ( v10 >= 0 )
  {
    if ( *((_QWORD *)v7 + 6) )
    {
      v15 = 0;
      *a4 = v7;
      if ( v11 )
      {
        LocalFree(v11);
        SecurityDescriptor = 0;
      }
      v8 = 0;
    }
    else
    {
      v12 = v10 | 0x90000000;
      if ( SecurityDescriptor )
      {
        LocalFree(SecurityDescriptor);
        SecurityDescriptor = 0;
      }
      v8 = v12;
    }
    goto LABEL_24;
  }
  v8 = v10 | 0x10000000;
  if ( SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
    SecurityDescriptor = 0;
  }
  AlpcPort::`scalar deleting destructor'(v7, 1u);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18007812c  mov     [rsp-8+arg_0], rbx
0x180078131  mov     [rsp-8+arg_8], rsi
0x180078136  push    rbp
0x180078137  push    rdi
0x180078138  push    r14
0x18007813a  lea     rbp, [rsp-30h]
0x18007813f  sub     rsp, 130h
0x180078146  mov     rax, cs:__security_cookie
0x18007814d  xor     rax, rsp
0x180078150  mov     [rbp+40h+var_20], rax
0x180078154  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007815b  mov     qword ptr [r9], 0
0x180078162  mov     ecx, 1F8h; unsigned __int64
0x180078167  mov     r14, r9
0x18007816a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18007816f  test    rax, rax
0x180078172  jz      loc_1800782FD
0x180078178  xor     edx, edx; unsigned __int16
0x18007817a  mov     rcx, rax; this
0x18007817d  call    ??0AlpcPort@@AEAA@G@Z; AlpcPort::AlpcPort(ushort)
0x180078182  mov     [rsp+140h+var_118], rax
0x180078187  mov     rsi, rax
0x18007818a  test    rax, rax
0x18007818d  jz      loc_180078306
0x180078193  mov     rcx, rax; this
0x180078196  call    ?Initialize@SipcPort@@IEAAJXZ; SipcPort::Initialize(void)
0x18007819b  mov     ebx, eax
0x18007819d  test    eax, eax
0x18007819f  js      loc_18007830B
0x1800781a5  mov     r8d, 1
0x1800781ab  lea     rdx, xmmword_1801F17C8
0x1800781b2  lea     rcx, [rsp+140h+var_E0]
0x1800781b7  call    ??0AlpcPortString@@QEAA@AEBU_GUID@@W4SIPC_SERVICE_BOUNDARY@@@Z; AlpcPortString::AlpcPortString(_GUID const &,SIPC_SERVICE_BOUNDARY)
0x1800781bc  mov     rax, cs:qword_1801D3A38
0x1800781c3  lea     r8, [rsp+140h+SecurityDescriptor]; SecurityDescriptor
0x1800781c8  movups  xmm0, cs:?c_serverObjectAttributes@AlpcPort@@0U_OBJECT_ATTRIBUTES@@B; _OBJECT_ATTRIBUTES const AlpcPort::c_serverObjectAttributes
0x1800781cf  mov     [rsp+140h+var_F8], rax
0x1800781d4  lea     rcx, ?c_serverDefaultSecurityDescriptor@AlpcPort@@0QBGB; "D:(A;;GA;;;WD)(A;;0x001F0001;;;AC)(A;;0"...
0x1800781db  mov     rax, cs:off_1801D3A48
0x1800781e2  xor     r9d, r9d; SecurityDescriptorSize
0x1800781e5  mov     [rsp+140h+var_E8], rax
0x1800781ea  lea     rax, [rsp+140h+var_E0]
0x1800781ef  mov     [rsp+140h+var_100], rax
0x1800781f4  movdqu  [rsp+140h+var_110], xmm0
0x1800781fa  lea     edx, [r9+1]; StringSDRevision
0x1800781fe  mov     [rsp+140h+var_F0], 0
0x180078207  mov     [rsp+140h+SecurityDescriptor], 0
0x180078210  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180078216  test    eax, eax
0x180078218  jnz     short loc_180078258
0x18007821a  call    cs:__imp_GetLastError
0x180078220  test    eax, eax
0x180078222  jle     short loc_18007822C
0x180078224  movzx   eax, ax
0x180078227  or      eax, 80070000h
0x18007822c  mov     rcx, [rsp+140h+SecurityDescriptor]; hMem
0x180078231  test    eax, eax
0x180078233  mov     ebx, 8000FFFFh
0x180078238  cmovs   ebx, eax
0x18007823b  test    rcx, rcx
0x18007823e  jz      loc_18007830B
0x180078244  call    cs:__imp_LocalFree
0x18007824a  mov     [rsp+140h+SecurityDescriptor], 0
0x180078253  jmp     loc_18007830B
0x180078258  mov     rax, [rsp+140h+SecurityDescriptor]
0x18007825d  lea     r8, ?c_serverPortAlpcAttributes@AlpcPort@@0U_ALPC_PORT_ATTRIBUTES@@B; _ALPC_PORT_ATTRIBUTES const AlpcPort::c_serverPortAlpcAttributes
0x180078264  lea     rdx, [rsp+140h+var_110]
0x180078269  mov     [rsp+140h+var_F0], rax
0x18007826e  lea     rcx, [rsi+30h]
0x180078272  call    cs:__imp_NtAlpcCreatePort
0x180078278  mov     rcx, [rsp+140h+SecurityDescriptor]; hMem
0x18007827d  mov     edi, eax
0x18007827f  test    eax, eax
0x180078281  jns     short loc_1800782B4
0x180078283  or      edi, 10000000h
0x180078289  mov     ebx, 8000FFFFh
0x18007828e  cmovl   ebx, edi
0x180078291  test    rcx, rcx
0x180078294  jz      short loc_1800782A5
0x180078296  call    cs:__imp_LocalFree
0x18007829c  mov     [rsp+140h+SecurityDescriptor], 0
0x1800782a5  mov     edx, 1; unsigned int
0x1800782aa  mov     rcx, rsi; this
0x1800782ad  call    ??_GAlpcPort@@UEAAPEAXI@Z; AlpcPort::`scalar deleting destructor'(uint)
0x1800782b2  jmp     short loc_180078315
0x1800782b4  cmp     qword ptr [rsi+30h], 0
0x1800782b9  jnz     short loc_1800782D9
0x1800782bb  or      edi, 90000000h
0x1800782c1  test    rcx, rcx
0x1800782c4  jz      short loc_1800782D5
0x1800782c6  call    cs:__imp_LocalFree
0x1800782cc  mov     [rsp+140h+SecurityDescriptor], 0
0x1800782d5  mov     ebx, edi
0x1800782d7  jmp     short loc_18007830B
0x1800782d9  mov     [rsp+140h+var_118], 0
0x1800782e2  mov     [r14], rsi
0x1800782e5  test    rcx, rcx
0x1800782e8  jz      short loc_1800782F9
0x1800782ea  call    cs:__imp_LocalFree
0x1800782f0  mov     [rsp+140h+SecurityDescriptor], 0
0x1800782f9  xor     ebx, ebx
0x1800782fb  jmp     short loc_18007830B
0x1800782fd  mov     [rsp+140h+var_118], 0
0x180078306  mov     ebx, 8007000Eh
0x18007830b  lea     rcx, [rsp+140h+var_118]
0x180078310  call    ??1?$unique_ptr@VAlpcPort@@U?$default_delete@VAlpcPort@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<AlpcPort,utl::default_delete<AlpcPort>>::~unique_ptr<AlpcPort,utl::default_delete<AlpcPort>>(void)
0x180078315  mov     eax, ebx
0x180078317  mov     rcx, [rbp+40h+var_20]
0x18007831b  xor     rcx, rsp; StackCookie
0x18007831e  call    __security_check_cookie
0x180078323  lea     r11, [rsp+140h+var_10]
0x18007832b  mov     rbx, [r11+20h]
0x18007832f  mov     rsi, [r11+28h]
0x180078333  mov     rsp, r11
0x180078336  pop     r14
0x180078338  pop     rdi
0x180078339  pop     rbp
0x18007833a  retn
```
