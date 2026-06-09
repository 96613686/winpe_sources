# SspLogMinimumSecurityFailure

- ea: `0x1800511ec`
- end: `0x180051350`
- name: `SspLogMinimumSecurityFailure`
- size: `356`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800157b0`
- `0x1800268dc`
- `0x18002ae74`
- `0x18002ba90`

## callees

- `0x18002e3e8`
- `0x18002fb50`
- `0x1800511ec`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051327`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051327`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180051286`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180051286`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800512a3`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800512a3`
- `ntdll!EtwEventEnabled` at `0x180051257`
- `ntdll!EtwEventEnabled` at `0x180051257`
- `ntdll!EtwEventWrite` at `0x180051319`
- `ntdll!EtwEventWrite` at `0x180051319`

## pseudocode

```c
int __fastcall SspLogMinimumSecurityFailure(DWORD a1, int a2, int a3, int a4)
{
  int result; // eax
  __int64 *v6; // rdi
  HANDLE v7; // rax
  void *v8; // rbx
  DWORD dwProcessId; // [rsp+28h] [rbp-E0h] BYREF
  DWORD dwSize[2]; // [rsp+30h] [rbp-D8h] BYREF
  DWORD *p_dwProcessId; // [rsp+38h] [rbp-D0h]
  __int64 v12; // [rsp+40h] [rbp-C8h]
  WCHAR *v13; // [rsp+48h] [rbp-C0h]
  __int64 v14; // [rsp+50h] [rbp-B8h]
  int *v15; // [rsp+58h] [rbp-B0h]
  __int64 v16; // [rsp+60h] [rbp-A8h]
  int *v17; // [rsp+68h] [rbp-A0h]
  __int64 v18; // [rsp+70h] [rbp-98h]
  WCHAR ExeName[264]; // [rsp+78h] [rbp-90h] BYREF
  int v20; // [rsp+2C0h] [rbp+1B8h] BYREF
  int v21; // [rsp+2C8h] [rbp+1C0h] BYREF

  v21 = a3;
  v20 = a2;
  dwProcessId = a1;
  dwSize[0] = 261;
  result = SspInitEtwLogHandle();
  if ( result >= 0 )
  {
    v6 = NTLMMinimumClientSecurity;
    if ( !a4 )
      v6 = NTLMMinimumServerSecurity;
    result = EtwEventEnabled(MsvEtwLogHandle, v6);
    if ( (_BYTE)result )
    {
      p_dwProcessId = &dwProcessId;
      v12 = 4;
      v7 = OpenProcess(0x1000u, 0, dwProcessId);
      v8 = v7;
      if ( v7 && QueryFullProcessImageNameW(v7, 0, ExeName, dwSize) && dwSize[0] )
      {
        v13 = ExeName;
        v14 = 2 * dwSize[0] + 2;
      }
      else
      {
        v14 = 4;
        v13 = L"-";
      }
      v15 = &v20;
      v16 = 4;
      v17 = &v21;
      v18 = 4;
      result = EtwEventWrite(MsvEtwLogHandle, v6, 4);
      if ( v8 )
        return CloseHandle(v8);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800511ec  mov     rax, rsp
0x1800511ef  mov     [rax+20h], rbx
0x1800511f3  mov     [rax+18h], r8d
0x1800511f7  mov     [rax+10h], edx
0x1800511fa  push    rbp
0x1800511fb  push    rdi
0x1800511fc  push    r14
0x1800511fe  lea     rbp, [rax-1A8h]
0x180051205  sub     rsp, 290h
0x18005120c  mov     rax, cs:__security_cookie
0x180051213  xor     rax, rsp
0x180051216  mov     [rbp+1A0h+var_20], rax
0x18005121d  mov     ebx, r9d
0x180051220  mov     [rsp+2A0h+dwProcessId], ecx
0x180051224  mov     [rsp+2A0h+dwSize], 105h
0x18005122c  call    SspInitEtwLogHandle
0x180051231  test    eax, eax
0x180051233  js      loc_18005132D
0x180051239  mov     rcx, cs:MsvEtwLogHandle
0x180051240  lea     rax, NTLMMinimumServerSecurity
0x180051247  test    ebx, ebx
0x180051249  lea     rdi, NTLMMinimumClientSecurity
0x180051250  cmovz   rdi, rax
0x180051254  mov     rdx, rdi
0x180051257  call    cs:__imp_EtwEventEnabled
0x18005125d  test    al, al
0x18005125f  jz      loc_18005132D
0x180051265  mov     r8d, [rsp+2A0h+dwProcessId]; dwProcessId
0x18005126a  lea     rax, [rsp+2A0h+dwProcessId]
0x18005126f  mov     r14d, 4
0x180051275  mov     [rsp+2A0h+var_270], rax
0x18005127a  xor     edx, edx; bInheritHandle
0x18005127c  mov     [rsp+2A0h+var_268], r14
0x180051281  mov     ecx, 1000h; dwDesiredAccess
0x180051286  call    cs:__imp_OpenProcess
0x18005128c  mov     rbx, rax
0x18005128f  test    rax, rax
0x180051292  jz      short loc_1800512D4
0x180051294  lea     r9, [rsp+2A0h+dwSize]; lpdwSize
0x180051299  xor     edx, edx; dwFlags
0x18005129b  lea     r8, [rsp+2A0h+ExeName]; lpExeName
0x1800512a0  mov     rcx, rax; hProcess
0x1800512a3  call    cs:__imp_QueryFullProcessImageNameW
0x1800512a9  test    eax, eax
0x1800512ab  jz      short loc_1800512D4
0x1800512ad  mov     eax, [rsp+2A0h+dwSize]
0x1800512b1  test    eax, eax
0x1800512b3  jz      short loc_1800512D4
0x1800512b5  lea     rcx, [rsp+2A0h+ExeName]
0x1800512ba  mov     dword ptr [rsp+2A0h+var_258+4], 0
0x1800512c2  lea     eax, ds:2[rax*2]
0x1800512c9  mov     [rsp+2A0h+var_260], rcx
0x1800512ce  mov     dword ptr [rsp+2A0h+var_258], eax
0x1800512d2  jmp     short loc_1800512E5
0x1800512d4  lea     rax, asc_1800745A0; "-"
0x1800512db  mov     [rsp+2A0h+var_258], r14
0x1800512e0  mov     [rsp+2A0h+var_260], rax
0x1800512e5  mov     rcx, cs:MsvEtwLogHandle
0x1800512ec  lea     rax, [rbp+1A0h+arg_8]
0x1800512f3  mov     [rsp+2A0h+var_250], rax
0x1800512f8  lea     r9, [rsp+2A0h+var_270]
0x1800512fd  lea     rax, [rbp+1A0h+arg_10]
0x180051304  mov     [rsp+2A0h+var_248], r14
0x180051309  mov     r8d, r14d
0x18005130c  mov     [rsp+2A0h+var_240], rax
0x180051311  mov     rdx, rdi
0x180051314  mov     [rsp+2A0h+var_238], r14
0x180051319  call    cs:__imp_EtwEventWrite
0x18005131f  test    rbx, rbx
0x180051322  jz      short loc_18005132D
0x180051324  mov     rcx, rbx; hObject
0x180051327  call    cs:__imp_CloseHandle
0x18005132d  mov     rcx, [rbp+1A0h+var_20]
0x180051334  xor     rcx, rsp; StackCookie
0x180051337  call    __security_check_cookie
0x18005133c  mov     rbx, [rsp+2A0h+arg_18]
0x180051344  add     rsp, 290h
0x18005134b  pop     r14
0x18005134d  pop     rdi
0x18005134e  pop     rbp
0x18005134f  retn
```
