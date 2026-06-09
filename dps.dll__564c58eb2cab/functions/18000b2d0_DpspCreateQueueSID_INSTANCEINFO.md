# DpspCreateQueueSID(INSTANCEINFO *)

- ea: `0x18000b2d0`
- end: `0x18000b3d4`
- name: `?DpspCreateQueueSID@@YAJPEAUINSTANCEINFO@@@Z`
- size: `260`
- prototype: `__int64 __fastcall(struct INSTANCEINFO *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004864`
- `0x180004de4`

## callees

- `0x1800013a0`
- `0x180009090`
- `0x18000a856`
- `0x18000b2d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b393`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b393`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000b31e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000b31e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000b385`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000b385`

## string_xrefs

- `0x18000b353`: `DpspCreateQueueSID`

## pseudocode

```c
__int64 __fastcall DpspCreateQueueSID(struct INSTANCEINFO *a1)
{
  signed int Args; // ebx
  PSID v3; // rax
  size_t LengthSid; // rbx
  void *v5; // rax
  signed int LastError; // eax

  Args = 0;
  if ( !*((_QWORD *)a1 + 95) )
  {
    v3 = (PSID)*((_QWORD *)a1 + 96);
    if ( v3 == g_pAdminSid || v3 == g_pEveryoneSid || !v3 )
    {
      *((_QWORD *)a1 + 95) = v3;
    }
    else
    {
      LengthSid = GetLengthSid(*((PSID *)a1 + 96));
      v5 = (void *)WdipAlloc(LengthSid);
      *((_QWORD *)a1 + 95) = v5;
      if ( v5 )
      {
        memset_0(v5, 0, LengthSid);
        if ( CopySid(LengthSid, *((PSID *)a1 + 95), *((PSID *)a1 + 96)) )
        {
          return 0;
        }
        else
        {
          LastError = GetLastError();
          Args = LastError;
          if ( LastError > 0 )
            Args = (unsigned __int16)LastError | 0x80070000;
          if ( Args < 0 )
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
              (int)L"DpspCreateQueueSID",
              529,
              (int)L"Error = %d",
              Args);
        }
      }
      else
      {
        Args = -2147024882;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
          (int)L"DpspCreateQueueSID",
          522,
          (int)L"Error = %d",
          14);
      }
    }
  }
  return (unsigned int)Args;
}

```

## disassembly

```asm
0x18000b2d0  mov     [rsp+arg_0], rbx
0x18000b2d5  mov     [rsp+arg_8], rsi
0x18000b2da  push    rdi
0x18000b2db  sub     rsp, 30h
0x18000b2df  xor     ebx, ebx
0x18000b2e1  mov     rdi, rcx
0x18000b2e4  cmp     [rcx+2F8h], rbx
0x18000b2eb  jnz     loc_18000B3C2
0x18000b2f1  mov     rax, [rcx+300h]
0x18000b2f8  cmp     rax, cs:g_pAdminSid
0x18000b2ff  jz      loc_18000B3BB
0x18000b305  cmp     rax, cs:g_pEveryoneSid
0x18000b30c  jz      loc_18000B3BB
0x18000b312  test    rax, rax
0x18000b315  jz      loc_18000B3BB
0x18000b31b  mov     rcx, rax; pSid
0x18000b31e  call    cs:__imp_GetLengthSid
0x18000b324  mov     ecx, eax
0x18000b326  mov     ebx, eax
0x18000b328  call    WdipAlloc
0x18000b32d  mov     [rdi+2F8h], rax
0x18000b334  test    rax, rax
0x18000b337  jnz     short loc_18000B368
0x18000b339  mov     ebx, 8007000Eh
0x18000b33e  mov     dword ptr [rsp+38h+Args], 0Eh; Args
0x18000b346  mov     r8d, 20Ah; int
0x18000b34c  lea     r9, aErrorD; "Error = %d"
0x18000b353  lea     rdx, aDpspcreatequeu; "DpspCreateQueueSID"
0x18000b35a  lea     rcx, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000b361  call    WdipTraceError
0x18000b366  jmp     short loc_18000B3C2
0x18000b368  mov     r8, rbx; Size
0x18000b36b  xor     edx, edx; Val
0x18000b36d  mov     rcx, rax; void *
0x18000b370  call    memset_0
0x18000b375  mov     r8, [rdi+300h]; pSourceSid
0x18000b37c  mov     ecx, ebx; nDestinationSidLength
0x18000b37e  mov     rdx, [rdi+2F8h]; pDestinationSid
0x18000b385  call    cs:__imp_CopySid
0x18000b38b  test    eax, eax
0x18000b38d  jz      short loc_18000B393
0x18000b38f  xor     ebx, ebx
0x18000b391  jmp     short loc_18000B3C2
0x18000b393  call    cs:__imp_GetLastError
0x18000b399  mov     ebx, eax
0x18000b39b  test    eax, eax
0x18000b39d  jle     short loc_18000B3A8
0x18000b39f  movzx   ebx, ax
0x18000b3a2  or      ebx, 80070000h
0x18000b3a8  test    ebx, ebx
0x18000b3aa  jns     short loc_18000B3C2
0x18000b3ac  movzx   eax, bx
0x18000b3af  mov     r8d, 211h
0x18000b3b5  mov     dword ptr [rsp+38h+Args], eax
0x18000b3b9  jmp     short loc_18000B34C
0x18000b3bb  mov     [rcx+2F8h], rax
0x18000b3c2  mov     rsi, [rsp+38h+arg_8]
0x18000b3c7  mov     eax, ebx
0x18000b3c9  mov     rbx, [rsp+38h+arg_0]
0x18000b3ce  add     rsp, 30h
0x18000b3d2  pop     rdi
0x18000b3d3  retn
```
