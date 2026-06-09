# WxGetProcessAppContainerSID(_SID *,ulong)

- ea: `0x1800c9c44`
- end: `0x1800c9d11`
- name: `?WxGetProcessAppContainerSID@@YAJPEAU_SID@@K@Z`
- size: `205`
- prototype: `__int64 __fastcall(PSID pDestinationSid, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800af000`

## callees

- `0x1800c9c44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9c79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9cdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9c79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9cdc`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800c9c69`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800c9c69`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800c9ccc`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800c9ccc`

## pseudocode

```c
signed int __fastcall WxGetProcessAppContainerSID(PSID pDestinationSid)
{
  signed int result; // eax

  if ( InitOnceExecuteOnce(&g_ProcessUserSIDInitOnce, (PINIT_ONCE_FN)_ProcessUserSIDInitOnceCallback, 0, 0) )
  {
    if ( g_fIsProcessAppContainer )
    {
      if ( CopySid(0x44u, pDestinationSid, &g_rgbAppContainerSID) )
      {
        return 0;
      }
      else
      {
        result = GetLastError();
        if ( result > 0 )
          result = (unsigned __int16)result | 0x80070000;
        if ( result >= 0 )
          return -2147418113;
      }
    }
    else
    {
      return -2147418113;
    }
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    if ( result >= 0 )
      return -2147418113;
  }
  return result;
}

```

## disassembly

```asm
0x1800c9c44  push    rbx
0x1800c9c46  sub     rsp, 20h
0x1800c9c4a  mov     rbx, rcx
0x1800c9c4d  mov     [rsp+28h+arg_14], 0
0x1800c9c55  lea     rcx, ?g_ProcessUserSIDInitOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1800c9c5c  xor     r9d, r9d; Context
0x1800c9c5f  xor     r8d, r8d; Parameter
0x1800c9c62  lea     rdx, ?_ProcessUserSIDInitOnceCallback@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800c9c69  call    cs:__imp_InitOnceExecuteOnce
0x1800c9c70  nop     dword ptr [rax+rax+00h]
0x1800c9c75  test    eax, eax
0x1800c9c77  jnz     short loc_1800C9CA5
0x1800c9c79  call    cs:__imp_GetLastError
0x1800c9c80  nop     dword ptr [rax+rax+00h]
0x1800c9c85  test    eax, eax
0x1800c9c87  jle     short loc_1800C9C91
0x1800c9c89  movzx   eax, ax
0x1800c9c8c  or      eax, 80070000h
0x1800c9c91  test    eax, eax
0x1800c9c93  mov     [rsp+28h+arg_14], 0C9h
0x1800c9c9b  mov     ecx, 8000FFFFh
0x1800c9ca0  cmovns  eax, ecx
0x1800c9ca3  jmp     short loc_1800C9D0A
0x1800c9ca5  cmp     cs:?g_fIsProcessAppContainer@@3HA, 0; int g_fIsProcessAppContainer
0x1800c9cac  jnz     short loc_1800C9CBD
0x1800c9cae  mov     eax, 8000FFFFh
0x1800c9cb3  mov     [rsp+28h+arg_14], 0CBh
0x1800c9cbb  jmp     short loc_1800C9D0A
0x1800c9cbd  lea     r8, ?g_rgbAppContainerSID@@3PAEA; pSourceSid
0x1800c9cc4  mov     rdx, rbx; pDestinationSid
0x1800c9cc7  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x1800c9ccc  call    cs:__imp_CopySid
0x1800c9cd3  nop     dword ptr [rax+rax+00h]
0x1800c9cd8  test    eax, eax
0x1800c9cda  jnz     short loc_1800C9D08
0x1800c9cdc  call    cs:__imp_GetLastError
0x1800c9ce3  nop     dword ptr [rax+rax+00h]
0x1800c9ce8  test    eax, eax
0x1800c9cea  jle     short loc_1800C9CF4
0x1800c9cec  movzx   eax, ax
0x1800c9cef  or      eax, 80070000h
0x1800c9cf4  test    eax, eax
0x1800c9cf6  mov     [rsp+28h+arg_14], 0CDh
0x1800c9cfe  mov     ecx, 8000FFFFh
0x1800c9d03  cmovns  eax, ecx
0x1800c9d06  jmp     short loc_1800C9D0A
0x1800c9d08  xor     eax, eax
0x1800c9d0a  add     rsp, 20h
0x1800c9d0e  pop     rbx
0x1800c9d0f  retn
```
