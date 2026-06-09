# PhoneCompanyAppDownloadActivity::GetEnterpriseId(ushort * *)

- ea: `0x1800770b8`
- end: `0x180077157`
- name: `?GetEnterpriseId@PhoneCompanyAppDownloadActivity@@AEAAJPEAPEAG@Z`
- size: `159`
- prototype: `__int64 __fastcall(PhoneCompanyAppDownloadActivity *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180077160`

## callees

- `0x1800770b8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180077141`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180077141`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800770d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180077133`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800770d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180077133`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800770ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800770ec`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x180077121`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x180077121`

## pseudocode

```c
int __fastcall PhoneCompanyAppDownloadActivity::GetEnterpriseId(
        PhoneCompanyAppDownloadActivity *this,
        unsigned __int16 **a2)
{
  int result; // eax
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // rdi
  HANDLE v7; // rax

  if ( !a2 )
    return -2147024809;
  *a2 = 0;
  ProcessHeap = GetProcessHeap();
  v5 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0xFFu);
  v6 = v5;
  if ( !v5 )
    return -2147024882;
  result = OmaDmRegistryGetString(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Enrollment\\AppMgmt",
             L"EnterpriseID",
             v5,
             0xFFu);
  if ( result == -2147024894 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
    return 1;
  }
  else
  {
    *a2 = v6;
  }
  return result;
}

```

## disassembly

```asm
0x1800770b8  mov     [rsp+arg_0], rbx
0x1800770bd  push    rdi
0x1800770be  sub     rsp, 30h
0x1800770c2  mov     rbx, rdx
0x1800770c5  test    rdx, rdx
0x1800770c8  jnz     short loc_1800770D1
0x1800770ca  mov     eax, 80070057h
0x1800770cf  jmp     short loc_18007714C
0x1800770d1  mov     qword ptr [rdx], 0
0x1800770d8  call    cs:__imp_GetProcessHeap
0x1800770de  mov     edx, 8; dwFlags
0x1800770e3  mov     r8d, 0FFh; dwBytes
0x1800770e9  mov     rcx, rax; hHeap
0x1800770ec  call    cs:__imp_HeapAlloc
0x1800770f2  mov     rdi, rax
0x1800770f5  test    rax, rax
0x1800770f8  jnz     short loc_180077101
0x1800770fa  mov     eax, 8007000Eh
0x1800770ff  jmp     short loc_18007714C
0x180077101  mov     r9, rdi
0x180077104  mov     [rsp+38h+var_18], 0FFh
0x18007710c  lea     r8, aEnterpriseid; "EnterpriseID"
0x180077113  mov     rcx, 0FFFFFFFF80000002h
0x18007711a  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Enrollment\\AppMgm"...
0x180077121  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x180077127  cmp     eax, 80070002h
0x18007712c  jz      short loc_180077133
0x18007712e  mov     [rbx], rdi
0x180077131  jmp     short loc_18007714C
0x180077133  call    cs:__imp_GetProcessHeap
0x180077139  mov     r8, rdi; lpMem
0x18007713c  xor     edx, edx; dwFlags
0x18007713e  mov     rcx, rax; hHeap
0x180077141  call    cs:__imp_HeapFree
0x180077147  mov     eax, 1
0x18007714c  mov     rbx, [rsp+38h+arg_0]
0x180077151  add     rsp, 30h
0x180077155  pop     rdi
0x180077156  retn
```
