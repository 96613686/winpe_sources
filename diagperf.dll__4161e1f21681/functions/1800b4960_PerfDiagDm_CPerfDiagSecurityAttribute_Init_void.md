# PerfDiagDm::CPerfDiagSecurityAttribute::Init(void)

- ea: `0x1800b4960`
- end: `0x1800b49ce`
- name: `?Init@CPerfDiagSecurityAttribute@PerfDiagDm@@QEAAJXZ`
- size: `110`
- prototype: `signed int __fastcall(PerfDiagDm::CPerfDiagSecurityAttribute *this)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180043150`
- `0x1800433e0`
- `0x180043758`
- `0x180043aac`

## callees

- `0x1800b4960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b49b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b49b2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800b498e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800b498e`
- `KERNEL32!LocalFree` at `0x1800b49a5`
- `KERNEL32!LocalFree` at `0x1800b49a5`

## pseudocode

```c
signed int __fastcall PerfDiagDm::CPerfDiagSecurityAttribute::Init(PerfDiagDm::CPerfDiagSecurityAttribute *this)
{
  PSECURITY_DESCRIPTOR *v1; // rbx
  signed int result; // eax

  v1 = (PSECURITY_DESCRIPTOR *)((char *)this + 8);
  *(_DWORD *)this = 24;
  if ( *((_QWORD *)this + 1) )
    return -2147467259;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:P(A;OICI;GA;;;SY)(A;OICI;GA;;;BA)(A;OICI;GR;;;WD)(A;OICI;GRGWSD;;;S-1-5-80-2970612574-78537857-698502321-5586"
          "74196-1451644582)(A;OICI;GRGWSD;;;S-1-5-80-3139157870-2983391045-3678747466-658725712-1809340420)",
         1u,
         v1,
         0) )
  {
    return 0;
  }
  result = -2147467259;
  if ( *v1 )
  {
    LocalFree(*v1);
    *v1 = 0;
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800b4960  push    rbx
0x1800b4962  sub     rsp, 20h
0x1800b4966  lea     rbx, [rcx+8]
0x1800b496a  mov     dword ptr [rcx], 18h
0x1800b4970  cmp     qword ptr [rbx], 0
0x1800b4974  jz      short loc_1800B497D
0x1800b4976  mov     eax, 80004005h
0x1800b497b  jmp     short loc_1800B49C8
0x1800b497d  xor     r9d, r9d; SecurityDescriptorSize
0x1800b4980  lea     rcx, StringSecurityDescriptor; "D:P(A;OICI;GA;;;SY)(A;OICI;GA;;;BA)(A;O"...
0x1800b4987  mov     r8, rbx; SecurityDescriptor
0x1800b498a  lea     edx, [r9+1]; StringSDRevision
0x1800b498e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800b4994  test    eax, eax
0x1800b4996  jnz     short loc_1800B49C6
0x1800b4998  mov     rcx, [rbx]; hMem
0x1800b499b  mov     eax, 80004005h
0x1800b49a0  test    rcx, rcx
0x1800b49a3  jz      short loc_1800B49C8
0x1800b49a5  call    cs:__imp_LocalFree
0x1800b49ab  mov     qword ptr [rbx], 0
0x1800b49b2  call    cs:__imp_GetLastError
0x1800b49b8  test    eax, eax
0x1800b49ba  jle     short loc_1800B49C8
0x1800b49bc  movzx   eax, ax
0x1800b49bf  or      eax, 80070000h
0x1800b49c4  jmp     short loc_1800B49C8
0x1800b49c6  xor     eax, eax
0x1800b49c8  add     rsp, 20h
0x1800b49cc  pop     rbx
0x1800b49cd  retn
```
