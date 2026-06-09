# SipcPrivateNamespace::GetSecurityDescriptor(void * *)

- ea: `0x180142860`
- end: `0x180142a6b`
- name: `?GetSecurityDescriptor@SipcPrivateNamespace@@AEAAJPEAPEAX@Z`
- size: `523`
- prototype: `__int64 __fastcall(SipcPrivateNamespace *__hidden this, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18014202c`

## callees

- `0x18002f9b4`
- `0x1800f0e70`
- `0x1800f2478`
- `0x180142860`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180142894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801429eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180142894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801429eb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18014288a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1801428e4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18014288a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1801428e4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801429e1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801429e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801428b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801428cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180142954`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180142967`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801429ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801429bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180142a10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180142a45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180142a58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801428b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801428cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180142954`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180142967`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801429ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801429bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180142a10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180142a45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180142a58`

## pseudocode

```c
__int64 __fastcall SipcPrivateNamespace::GetSecurityDescriptor(SipcPrivateNamespace *this, void **a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rax
  const WCHAR *v11; // rbx
  signed int v12; // eax
  HLOCAL hMem; // [rsp+60h] [rbp+30h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp+38h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp+40h] BYREF
  wchar_t *v16; // [rsp+78h] [rbp+48h] BYREF

  *a2 = 0;
  StringSid = 0;
  hMem = 0;
  if ( !ConvertSidToStringSidW((char *)this + 100, &StringSid)
    || !ConvertSidToStringSidW((char *)this + 168, (LPWSTR *)&hMem) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v5 = -2147418113;
    if ( LastError < 0 )
      v5 = LastError;
    goto LABEL_6;
  }
  v7 = -1;
  do
    ++v7;
  while ( StringSid[v7] );
  v8 = -1;
  do
    ++v8;
  while ( *((_WORD *)hMem + v8) );
  v9 = v8 + v7 + 54;
  v10 = 2 * v9;
  if ( !is_mul_ok(v9, 2u) )
    v10 = -1;
  v16 = (wchar_t *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v16;
  if ( !v16 )
  {
    VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&v16);
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    if ( StringSid )
      LocalFree(StringSid);
    return 2147942414LL;
  }
  if ( swprintf_s(v16, v9, L"S:(ML;;NW;;;LW)D:(A;;GA;;;WD)(A;;GA;;;%s)(A;;GA;;;%s)", StringSid, hMem) <= 0 )
  {
    VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&v16);
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    if ( StringSid )
      LocalFree(StringSid);
    return 2147549183LL;
  }
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v11, 1u, &SecurityDescriptor, 0) )
  {
    v12 = GetLastError();
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    v5 = -2147418113;
    if ( v12 < 0 )
      v5 = v12;
    if ( SecurityDescriptor )
    {
      LocalFree(SecurityDescriptor);
      SecurityDescriptor = 0;
    }
    VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&v16);
LABEL_6:
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    if ( StringSid )
      LocalFree(StringSid);
    return v5;
  }
  *a2 = SecurityDescriptor;
  SecurityDescriptor = 0;
  VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&v16);
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( StringSid )
    LocalFree(StringSid);
  return 0;
}

```

## disassembly

```asm
0x180142860  push    rbp
0x180142862  push    rbx
0x180142863  push    rsi
0x180142864  push    rdi
0x180142865  push    r14
0x180142867  mov     rbp, rsp
0x18014286a  sub     rsp, 30h
0x18014286e  xor     r14d, r14d
0x180142871  mov     rdi, rdx
0x180142874  mov     [rdx], r14
0x180142877  mov     rbx, rcx
0x18014287a  lea     rdx, [rbp+StringSid]; StringSid
0x18014287e  mov     [rbp+StringSid], r14
0x180142882  add     rcx, 64h ; 'd'; Sid
0x180142886  mov     [rbp+hMem], r14
0x18014288a  call    cs:__imp_ConvertSidToStringSidW
0x180142890  test    eax, eax
0x180142892  jnz     short loc_1801428D9
0x180142894  call    cs:__imp_GetLastError
0x18014289a  test    eax, eax
0x18014289c  jle     short loc_1801428A6
0x18014289e  movzx   eax, ax
0x1801428a1  or      eax, 80070000h
0x1801428a6  test    eax, eax
0x1801428a8  mov     ebx, 8000FFFFh
0x1801428ad  cmovs   ebx, eax
0x1801428b0  mov     rcx, [rbp+hMem]; hMem
0x1801428b4  test    rcx, rcx
0x1801428b7  jz      short loc_1801428C3
0x1801428b9  call    cs:__imp_LocalFree
0x1801428bf  mov     [rbp+hMem], r14
0x1801428c3  mov     rcx, [rbp+StringSid]; hMem
0x1801428c7  test    rcx, rcx
0x1801428ca  jz      short loc_1801428D2
0x1801428cc  call    cs:__imp_LocalFree
0x1801428d2  mov     eax, ebx
0x1801428d4  jmp     loc_180142A60
0x1801428d9  lea     rcx, [rbx+0A8h]; Sid
0x1801428e0  lea     rdx, [rbp+hMem]; StringSid
0x1801428e4  call    cs:__imp_ConvertSidToStringSidW
0x1801428ea  test    eax, eax
0x1801428ec  jz      short loc_180142894
0x1801428ee  mov     rcx, [rbp+StringSid]
0x1801428f2  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801428f6  mov     rax, r8
0x1801428f9  inc     rax
0x1801428fc  cmp     [rcx+rax*2], r14w
0x180142901  jnz     short loc_1801428F9
0x180142903  mov     rdx, [rbp+hMem]
0x180142907  mov     rcx, r8
0x18014290a  inc     rcx
0x18014290d  cmp     [rdx+rcx*2], r14w
0x180142912  jnz     short loc_18014290A
0x180142914  lea     rsi, [rax+36h]
0x180142918  mov     eax, 2
0x18014291d  add     rsi, rcx
0x180142920  mul     rsi
0x180142923  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18014292a  cmovb   rax, r8
0x18014292e  mov     rcx, rax; unsigned __int64
0x180142931  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180142936  mov     [rbp+arg_18], rax
0x18014293a  mov     rbx, rax
0x18014293d  test    rax, rax
0x180142940  jnz     short loc_180142977
0x180142942  lea     rcx, [rbp+arg_18]
0x180142946  call    ??1?$VariableSizedPayloadStorage@UInputInfo@@@@QEAA@XZ; VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(void)
0x18014294b  mov     rcx, [rbp+hMem]; hMem
0x18014294f  test    rcx, rcx
0x180142952  jz      short loc_18014295E
0x180142954  call    cs:__imp_LocalFree
0x18014295a  mov     [rbp+hMem], r14
0x18014295e  mov     rcx, [rbp+StringSid]; hMem
0x180142962  test    rcx, rcx
0x180142965  jz      short loc_18014296D
0x180142967  call    cs:__imp_LocalFree
0x18014296d  mov     eax, 8007000Eh
0x180142972  jmp     loc_180142A60
0x180142977  mov     rax, [rbp+hMem]
0x18014297b  lea     r8, aSMlNwLwDAGaWdA; "S:(ML;;NW;;;LW)D:(A;;GA;;;WD)(A;;GA;;;%"...
0x180142982  mov     r9, [rbp+StringSid]
0x180142986  mov     rdx, rsi; BufferCount
0x180142989  mov     rcx, rbx; Buffer
0x18014298c  mov     [rsp+30h+var_10], rax
0x180142991  call    swprintf_s
0x180142996  test    eax, eax
0x180142998  jg      short loc_1801429CF
0x18014299a  lea     rcx, [rbp+arg_18]
0x18014299e  call    ??1?$VariableSizedPayloadStorage@UInputInfo@@@@QEAA@XZ; VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(void)
0x1801429a3  mov     rcx, [rbp+hMem]; hMem
0x1801429a7  test    rcx, rcx
0x1801429aa  jz      short loc_1801429B6
0x1801429ac  call    cs:__imp_LocalFree
0x1801429b2  mov     [rbp+hMem], r14
0x1801429b6  mov     rcx, [rbp+StringSid]; hMem
0x1801429ba  test    rcx, rcx
0x1801429bd  jz      short loc_1801429C5
0x1801429bf  call    cs:__imp_LocalFree
0x1801429c5  mov     eax, 8000FFFFh
0x1801429ca  jmp     loc_180142A60
0x1801429cf  xor     r9d, r9d; SecurityDescriptorSize
0x1801429d2  mov     [rbp+SecurityDescriptor], r14
0x1801429d6  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1801429da  mov     rcx, rbx; StringSecurityDescriptor
0x1801429dd  lea     edx, [r9+1]; StringSDRevision
0x1801429e1  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1801429e7  test    eax, eax
0x1801429e9  jnz     short loc_180142A28
0x1801429eb  call    cs:__imp_GetLastError
0x1801429f1  test    eax, eax
0x1801429f3  jle     short loc_1801429FD
0x1801429f5  movzx   eax, ax
0x1801429f8  or      eax, 80070000h
0x1801429fd  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180142a01  test    eax, eax
0x180142a03  mov     ebx, 8000FFFFh
0x180142a08  cmovs   ebx, eax
0x180142a0b  test    rcx, rcx
0x180142a0e  jz      short loc_180142A1A
0x180142a10  call    cs:__imp_LocalFree
0x180142a16  mov     [rbp+SecurityDescriptor], r14
0x180142a1a  lea     rcx, [rbp+arg_18]
0x180142a1e  call    ??1?$VariableSizedPayloadStorage@UInputInfo@@@@QEAA@XZ; VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(void)
0x180142a23  jmp     loc_1801428B0
0x180142a28  mov     rax, [rbp+SecurityDescriptor]
0x180142a2c  lea     rcx, [rbp+arg_18]
0x180142a30  mov     [rdi], rax
0x180142a33  mov     [rbp+SecurityDescriptor], r14
0x180142a37  call    ??1?$VariableSizedPayloadStorage@UInputInfo@@@@QEAA@XZ; VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(void)
0x180142a3c  mov     rcx, [rbp+hMem]; hMem
0x180142a40  test    rcx, rcx
0x180142a43  jz      short loc_180142A4F
0x180142a45  call    cs:__imp_LocalFree
0x180142a4b  mov     [rbp+hMem], r14
0x180142a4f  mov     rcx, [rbp+StringSid]; hMem
0x180142a53  test    rcx, rcx
0x180142a56  jz      short loc_180142A5E
0x180142a58  call    cs:__imp_LocalFree
0x180142a5e  xor     eax, eax
0x180142a60  add     rsp, 30h
0x180142a64  pop     r14
0x180142a66  pop     rdi
0x180142a67  pop     rsi
0x180142a68  pop     rbx
0x180142a69  pop     rbp
0x180142a6a  retn
```
