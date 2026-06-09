# CreateDirectoryForSystemAndAdministrators(char const *)

- ea: `0x18000216c`
- end: `0x18000222f`
- name: `?CreateDirectoryForSystemAndAdministrators@@YAHPEBD@Z`
- size: `195`
- prototype: `__int64 __fastcall(LPCSTR lpPathName)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002c8c`

## callees

- `0x18000216c`

## import_xrefs

- `KERNEL32!CreateDirectoryA` at `0x1800021d7`
- `KERNEL32!CreateDirectoryA` at `0x1800021d7`
- `KERNEL32!SetLastError` at `0x180002217`
- `KERNEL32!SetLastError` at `0x180002217`
- `KERNEL32!GetLastError` at `0x1800021e3`
- `KERNEL32!GetLastError` at `0x1800021f9`
- `KERNEL32!GetLastError` at `0x1800021e3`
- `KERNEL32!GetLastError` at `0x1800021f9`
- `KERNEL32!LocalFree` at `0x180002206`
- `KERNEL32!LocalFree` at `0x180002206`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorA` at `0x1800021b3`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorA` at `0x1800021b3`

## pseudocode

```c
__int64 __fastcall CreateDirectoryForSystemAndAdministrators(LPCSTR lpPathName)
{
  __int64 v2; // rdx
  struct _SECURITY_ATTRIBUTES *p_SecurityDescriptor; // rax
  unsigned int v4; // edi
  DWORD LastError; // ebx
  struct _SECURITY_ATTRIBUTES SecurityDescriptor; // [rsp+20h] [rbp-28h] BYREF

  memset(&SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v2 = 24;
  p_SecurityDescriptor = &SecurityDescriptor;
  do
  {
    LOBYTE(p_SecurityDescriptor->nLength) = 0;
    p_SecurityDescriptor = (struct _SECURITY_ATTRIBUTES *)((char *)p_SecurityDescriptor + 1);
    --v2;
  }
  while ( v2 );
  v4 = ConvertStringSecurityDescriptorToSecurityDescriptorA(
         "D:P(A;OICI;GA;;;SY)(A;OICI;GA;;;BA)",
         1u,
         &SecurityDescriptor.lpSecurityDescriptor,
         0);
  if ( v4 )
  {
    SecurityDescriptor.nLength = 24;
    SecurityDescriptor.bInheritHandle = 0;
    v4 = CreateDirectoryA(lpPathName, &SecurityDescriptor);
    if ( !v4 )
      v4 = GetLastError() == 183;
  }
  if ( SecurityDescriptor.lpSecurityDescriptor )
  {
    LastError = GetLastError();
    LocalFree(SecurityDescriptor.lpSecurityDescriptor);
    SecurityDescriptor.lpSecurityDescriptor = 0;
    SetLastError(LastError);
  }
  return v4;
}

```

## disassembly

```asm
0x18000216c  mov     r11, rsp
0x18000216f  mov     [r11+8], rbx
0x180002173  mov     [r11+10h], rbp
0x180002177  push    rdi
0x180002178  sub     rsp, 40h
0x18000217c  xor     eax, eax
0x18000217e  xorps   xmm0, xmm0
0x180002181  movups  xmmword ptr [rsp+48h+SecurityDescriptor], xmm0
0x180002186  mov     [r11-18h], rax
0x18000218a  mov     rbx, rcx
0x18000218d  lea     edx, [rax+18h]
0x180002190  lea     ebp, [rdx-17h]
0x180002193  lea     rax, [r11-28h]
0x180002197  mov     byte ptr [rax], 0
0x18000219a  add     rax, rbp
0x18000219d  sub     rdx, rbp
0x1800021a0  jnz     short loc_180002197
0x1800021a2  xor     r9d, r9d; SecurityDescriptorSize
0x1800021a5  lea     r8, [rsp+48h+SecurityDescriptor+8]; SecurityDescriptor
0x1800021aa  mov     edx, ebp; StringSDRevision
0x1800021ac  lea     rcx, StringSecurityDescriptor; "D:P(A;OICI;GA;;;SY)(A;OICI;GA;;;BA)"
0x1800021b3  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorA
0x1800021b9  mov     edi, eax
0x1800021bb  test    eax, eax
0x1800021bd  jz      short loc_1800021F1
0x1800021bf  lea     rdx, [rsp+48h+SecurityDescriptor]; lpSecurityAttributes
0x1800021c4  mov     dword ptr [rsp+48h+SecurityDescriptor], 18h
0x1800021cc  mov     rcx, rbx; lpPathName
0x1800021cf  mov     [rsp+48h+var_18], 0
0x1800021d7  call    cs:__imp_CreateDirectoryA
0x1800021dd  mov     edi, eax
0x1800021df  test    eax, eax
0x1800021e1  jnz     short loc_1800021F1
0x1800021e3  call    cs:__imp_GetLastError
0x1800021e9  cmp     eax, 0B7h
0x1800021ee  cmovz   edi, ebp
0x1800021f1  cmp     [rsp+48h+SecurityDescriptor+8], 0
0x1800021f7  jz      short loc_18000221D
0x1800021f9  call    cs:__imp_GetLastError
0x1800021ff  mov     rcx, [rsp+48h+SecurityDescriptor+8]; hMem
0x180002204  mov     ebx, eax
0x180002206  call    cs:__imp_LocalFree
0x18000220c  mov     ecx, ebx; dwErrCode
0x18000220e  mov     [rsp+48h+SecurityDescriptor+8], 0
0x180002217  call    cs:__imp_SetLastError
0x18000221d  mov     rbx, [rsp+48h+arg_0]
0x180002222  mov     eax, edi
0x180002224  mov     rbp, [rsp+48h+arg_8]
0x180002229  add     rsp, 40h
0x18000222d  pop     rdi
0x18000222e  retn
```
