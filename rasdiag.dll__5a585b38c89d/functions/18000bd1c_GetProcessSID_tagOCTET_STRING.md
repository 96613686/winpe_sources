# GetProcessSID(tagOCTET_STRING *)

- ea: `0x18000bd1c`
- end: `0x18000beb2`
- name: `?GetProcessSID@@YAJPEAUtagOCTET_STRING@@@Z`
- size: `406`
- prototype: `__int64 __fastcall(struct tagOCTET_STRING *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180009e60`
- `0x18000ad60`

## callees

- `0x180002676`
- `0x18000bd1c`
- `0x18000ded2`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000be5f`
- `KERNEL32!CloseHandle` at `0x18000be5f`
- `KERNEL32!GetCurrentThread` at `0x18000bd82`
- `KERNEL32!GetCurrentThread` at `0x18000bd82`
- `KERNEL32!SetLastError` at `0x18000bd5f`
- `KERNEL32!SetLastError` at `0x18000be0e`
- `KERNEL32!SetLastError` at `0x18000bd5f`
- `KERNEL32!SetLastError` at `0x18000be0e`
- `KERNEL32!GetLastError` at `0x18000be3f`
- `KERNEL32!GetLastError` at `0x18000be6d`
- `KERNEL32!GetLastError` at `0x18000be3f`
- `KERNEL32!GetLastError` at `0x18000be6d`
- `ADVAPI32!OpenThreadToken` at `0x18000bd9e`
- `ADVAPI32!OpenThreadToken` at `0x18000bd9e`
- `ADVAPI32!GetLengthSid` at `0x18000bde7`
- `ADVAPI32!GetLengthSid` at `0x18000bde7`
- `ADVAPI32!GetTokenInformation` at `0x18000bdd4`
- `ADVAPI32!GetTokenInformation` at `0x18000bdd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bd48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bdf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bd48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bdf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be8b`

## pseudocode

```c
__int64 __fastcall GetProcessSID(struct tagOCTET_STRING *a1)
{
  PSID *v2; // rax
  PSID *v3; // rdi
  unsigned int v4; // ebx
  HANDLE CurrentThread; // rax
  SIZE_T LengthSid; // rbp
  BYTE *v7; // rsi
  signed int LastError; // eax
  signed int v9; // eax
  DWORD ReturnLength; // [rsp+60h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+10h] BYREF

  TokenHandle = 0;
  if ( a1 )
  {
    v2 = (PSID *)CoTaskMemAlloc(0x4000u);
    v3 = v2;
    if ( v2 )
    {
      memset_0(v2, 0, 0x4000u);
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 0x20008u, 0, &TokenHandle) )
      {
        ReturnLength = 0;
        if ( GetTokenInformation(TokenHandle, TokenUser, v3, 0x4000u, &ReturnLength) )
        {
          LengthSid = GetLengthSid(*v3);
          v7 = (BYTE *)CoTaskMemAlloc(LengthSid);
          if ( !v7 )
            SetLastError(8u);
          a1->lpValue = v7;
          if ( v7 )
          {
            v4 = 0;
            memcpy_0(v7, *v3, LengthSid);
            a1->dwLength = LengthSid;
          }
          else
          {
            v4 = -2147024882;
          }
        }
        else
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
        }
        CloseHandle(TokenHandle);
      }
      else
      {
        v9 = GetLastError();
        v4 = v9;
        if ( v9 > 0 )
          v4 = (unsigned __int16)v9 | 0x80070000;
      }
      CoTaskMemFree(v3);
    }
    else
    {
      SetLastError(8u);
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x18000bd1c  mov     [rsp+arg_10], rbx
0x18000bd21  push    rbp
0x18000bd22  push    rsi
0x18000bd23  push    rdi
0x18000bd24  push    r14
0x18000bd26  push    r15
0x18000bd28  sub     rsp, 30h
0x18000bd2c  mov     [rsp+58h+TokenHandle], 0
0x18000bd35  mov     r14, rcx
0x18000bd38  test    rcx, rcx
0x18000bd3b  jz      loc_18000BE99
0x18000bd41  mov     ebx, 4000h
0x18000bd46  mov     ecx, ebx; cb
0x18000bd48  call    cs:__imp_CoTaskMemAlloc
0x18000bd4f  nop     dword ptr [rax+rax+00h]
0x18000bd54  mov     rdi, rax
0x18000bd57  test    rax, rax
0x18000bd5a  jnz     short loc_18000BD75
0x18000bd5c  lea     ecx, [rax+8]; dwErrCode
0x18000bd5f  call    cs:__imp_SetLastError
0x18000bd66  nop     dword ptr [rax+rax+00h]
0x18000bd6b  mov     ebx, 8007000Eh
0x18000bd70  jmp     loc_18000BE9E
0x18000bd75  mov     r8, rbx; Size
0x18000bd78  xor     edx, edx; Val
0x18000bd7a  mov     rcx, rdi; void *
0x18000bd7d  call    memset_0
0x18000bd82  call    cs:__imp_GetCurrentThread
0x18000bd89  nop     dword ptr [rax+rax+00h]
0x18000bd8e  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x18000bd93  xor     r8d, r8d; OpenAsSelf
0x18000bd96  mov     rcx, rax; ThreadHandle
0x18000bd99  mov     edx, 20008h; DesiredAccess
0x18000bd9e  call    cs:__imp_OpenThreadToken
0x18000bda5  nop     dword ptr [rax+rax+00h]
0x18000bdaa  test    eax, eax
0x18000bdac  jz      loc_18000BE6D
0x18000bdb2  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18000bdb7  lea     rax, [rsp+58h+arg_0]
0x18000bdbc  mov     r9d, ebx; TokenInformationLength
0x18000bdbf  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000bdc4  mov     r8, rdi; TokenInformation
0x18000bdc7  mov     [rsp+58h+arg_0], 0
0x18000bdcf  mov     edx, 1; TokenInformationClass
0x18000bdd4  call    cs:__imp_GetTokenInformation
0x18000bddb  nop     dword ptr [rax+rax+00h]
0x18000bde0  test    eax, eax
0x18000bde2  jz      short loc_18000BE3F
0x18000bde4  mov     rcx, [rdi]; pSid
0x18000bde7  call    cs:__imp_GetLengthSid
0x18000bdee  nop     dword ptr [rax+rax+00h]
0x18000bdf3  mov     ecx, eax; cb
0x18000bdf5  mov     ebp, eax
0x18000bdf7  call    cs:__imp_CoTaskMemAlloc
0x18000bdfe  nop     dword ptr [rax+rax+00h]
0x18000be03  mov     rsi, rax
0x18000be06  test    rax, rax
0x18000be09  jnz     short loc_18000BE1A
0x18000be0b  lea     ecx, [rax+8]; dwErrCode
0x18000be0e  call    cs:__imp_SetLastError
0x18000be15  nop     dword ptr [rax+rax+00h]
0x18000be1a  mov     [r14+8], rsi
0x18000be1e  test    rsi, rsi
0x18000be21  jz      short loc_18000BE38
0x18000be23  mov     rdx, [rdi]; Src
0x18000be26  xor     ebx, ebx
0x18000be28  mov     r8, rbp; Size
0x18000be2b  mov     rcx, rsi; void *
0x18000be2e  call    memcpy_0
0x18000be33  mov     [r14], ebp
0x18000be36  jmp     short loc_18000BE5A
0x18000be38  mov     ebx, 8007000Eh
0x18000be3d  jmp     short loc_18000BE5A
0x18000be3f  call    cs:__imp_GetLastError
0x18000be46  nop     dword ptr [rax+rax+00h]
0x18000be4b  mov     ebx, eax
0x18000be4d  test    eax, eax
0x18000be4f  jle     short loc_18000BE5A
0x18000be51  movzx   ebx, ax
0x18000be54  or      ebx, 80070000h
0x18000be5a  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18000be5f  call    cs:__imp_CloseHandle
0x18000be66  nop     dword ptr [rax+rax+00h]
0x18000be6b  jmp     short loc_18000BE88
0x18000be6d  call    cs:__imp_GetLastError
0x18000be74  nop     dword ptr [rax+rax+00h]
0x18000be79  mov     ebx, eax
0x18000be7b  test    eax, eax
0x18000be7d  jle     short loc_18000BE88
0x18000be7f  movzx   ebx, ax
0x18000be82  or      ebx, 80070000h
0x18000be88  mov     rcx, rdi; pv
0x18000be8b  call    cs:__imp_CoTaskMemFree
0x18000be92  nop     dword ptr [rax+rax+00h]
0x18000be97  jmp     short loc_18000BE9E
0x18000be99  mov     ebx, 80070057h
0x18000be9e  mov     eax, ebx
0x18000bea0  mov     rbx, [rsp+58h+arg_10]
0x18000bea5  add     rsp, 30h
0x18000bea9  pop     r15
0x18000beab  pop     r14
0x18000bead  pop     rdi
0x18000beae  pop     rsi
0x18000beaf  pop     rbp
0x18000beb0  retn
```
