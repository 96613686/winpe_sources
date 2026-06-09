# CopyStringW(ushort const *,unsigned __int64,ushort * *)

- ea: `0x180010dd0`
- end: `0x180010fa0`
- name: `?CopyStringW@@YAJPEBG_KPEAPEAG@Z`
- size: `464`
- prototype: `__int64 __fastcall(const unsigned __int16 *Source, unsigned __int64, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008ad0`
- `0x18002aee4`
- `0x180044364`

## callees

- `0x180010dd0`
- `0x180027278`
- `0x180027448`
- `0x1800274cc`
- `0x18002bc58`
- `0x18002e664`
- `0x18002e814`
- `0x18002f710`
- `0x180046ce0`

## string_xrefs

- `0x180010e96`: `CopyStringW`
- `0x180010f24`: `CopyStringW`
- `0x180010f4d`: `CopyStringW`
- `0x180010f83`: `CopyStringW`
- `0x180010f09`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x180010f02`: `EventWriteNullOrEmptyParameterFailureEvent`

## pseudocode

```c
__int64 __fastcall CopyStringW(const unsigned __int16 *Source, __int64 a2, unsigned __int16 **a3)
{
  unsigned __int16 *v6; // rbx
  unsigned __int64 v7; // rax
  unsigned __int16 *v8; // rax
  rsize_t v9; // r14
  unsigned int v10; // eax
  signed int v11; // edi
  __int64 v13; // r8
  unsigned int v14; // eax
  _BYTE v15[16]; // [rsp+30h] [rbp-68h] BYREF
  const unsigned __int16 *v16; // [rsp+40h] [rbp-58h]
  __int64 v17; // [rsp+48h] [rbp-50h]
  const wchar_t *v18; // [rsp+50h] [rbp-48h]
  __int64 v19; // [rsp+58h] [rbp-40h]

  v6 = 0;
  if ( a3 )
  {
    *a3 = 0;
    if ( Source )
    {
      v7 = 2 * (a2 + 1);
      if ( !is_mul_ok(a2 + 1, 2u) )
        v7 = -1;
      v8 = (unsigned __int16 *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
      v6 = v8;
      if ( v8 )
      {
        v9 = 2 * a2;
        v10 = memcpy_s_0(v8, v9, Source, v9);
        v11 = v10;
        if ( v10 )
        {
          Logger::TraceError(L"%s: wmemcpy_s failed with error code: 0x%08x.", L"CopyStringW", v10);
          if ( v11 > 0 )
            v11 = (unsigned __int16)v11 | 0x80070000;
        }
        else
        {
          v6[v9 / 2] = 0;
          v11 = 0;
          *a3 = v6;
          v6 = 0;
        }
      }
      else
      {
        v11 = -2147024882;
        Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"CopyStringW");
      }
    }
    else
    {
      v11 = -2147024809;
      Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringW", L"source");
      Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringW", L"source");
    }
  }
  else
  {
    v11 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringW", L"pDest");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v16 = L"CopyStringW";
      v17 = 24;
      v18 = L"pDest";
      v19 = 12;
      v14 = McGenEventWrite_EventWriteTransfer(
              &UserDeviceRegistrationEventProvider_Context,
              NullOrEmptyParameterFailureEvent,
              v13,
              3,
              v15);
      if ( v14 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteNullOrEmptyParameterFailureEvent",
          L"EventWriteNullOrEmptyParameterFailureEvent",
          v14);
    }
  }
  operator delete(v6);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180010dd0  push    rbx
0x180010dd2  push    rbp
0x180010dd3  push    rsi
0x180010dd4  push    rdi
0x180010dd5  push    r14
0x180010dd7  sub     rsp, 70h
0x180010ddb  mov     rax, cs:__security_cookie
0x180010de2  xor     rax, rsp
0x180010de5  mov     [rsp+98h+var_38], rax
0x180010dea  xor     ebp, ebp
0x180010dec  mov     rsi, r8
0x180010def  mov     r14, rdx
0x180010df2  mov     rdi, rcx
0x180010df5  mov     ebx, ebp
0x180010df7  test    r8, r8
0x180010dfa  jz      loc_180010E8A
0x180010e00  mov     [r8], rbp
0x180010e03  test    rcx, rcx
0x180010e06  jz      loc_180010F4D
0x180010e0c  lea     rcx, [rdx+1]
0x180010e10  mov     eax, 2
0x180010e15  mul     rcx
0x180010e18  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180010e1f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010e26  cmovb   rax, rcx
0x180010e2a  mov     rcx, rax; unsigned __int64
0x180010e2d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180010e32  mov     rbx, rax
0x180010e35  test    rax, rax
0x180010e38  jz      loc_180010F83
0x180010e3e  add     r14, r14
0x180010e41  mov     r8, rdi; Source
0x180010e44  mov     r9, r14; SourceSize
0x180010e47  mov     rdx, r14; DestinationSize
0x180010e4a  mov     rcx, rax; Destination
0x180010e4d  call    memcpy_s_0
0x180010e52  mov     edi, eax
0x180010e54  test    eax, eax
0x180010e56  jnz     loc_180010F21
0x180010e5c  mov     [r14+rbx], bp
0x180010e61  mov     edi, ebp
0x180010e63  mov     [rsi], rbx
0x180010e66  mov     ebx, ebp
0x180010e68  mov     rcx, rbx; Block
0x180010e6b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010e70  mov     eax, edi
0x180010e72  mov     rcx, [rsp+98h+var_38]
0x180010e77  xor     rcx, rsp; StackCookie
0x180010e7a  call    __security_check_cookie
0x180010e7f  add     rsp, 70h
0x180010e83  pop     r14
0x180010e85  pop     rdi
0x180010e86  pop     rsi
0x180010e87  pop     rbp
0x180010e88  pop     rbx
0x180010e89  retn
0x180010e8a  lea     r14, aPdest; "pDest"
0x180010e91  mov     edi, 80070057h
0x180010e96  lea     rsi, aCopystringw; "CopyStringW"
0x180010e9d  mov     r8, r14
0x180010ea0  mov     rdx, rsi
0x180010ea3  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180010eaa  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180010eaf  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180010eb6  jz      short loc_180010E68
0x180010eb8  lea     rax, [rsp+98h+var_68]
0x180010ebd  mov     [rsp+98h+var_58], rsi
0x180010ec2  mov     r9d, 3
0x180010ec8  mov     [rsp+98h+var_78], rax
0x180010ecd  lea     rdx, NullOrEmptyParameterFailureEvent
0x180010ed4  mov     [rsp+98h+var_50], 18h
0x180010edd  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x180010ee4  mov     [rsp+98h+var_48], r14
0x180010ee9  mov     [rsp+98h+var_40], 0Ch
0x180010ef2  call    McGenEventWrite_EventWriteTransfer
0x180010ef7  test    eax, eax
0x180010ef9  jz      loc_180010E68
0x180010eff  mov     r9d, eax
0x180010f02  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x180010f09  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x180010f10  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180010f17  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180010f1c  jmp     loc_180010E68
0x180010f21  mov     r8d, edi
0x180010f24  lea     rdx, aCopystringw; "CopyStringW"
0x180010f2b  lea     rcx, aSWmemcpySFaile; "%s: wmemcpy_s failed with error code: 0"...
0x180010f32  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180010f37  test    edi, edi
0x180010f39  jle     loc_180010E68
0x180010f3f  movzx   edi, di
0x180010f42  or      edi, 80070000h
0x180010f48  jmp     loc_180010E68
0x180010f4d  lea     rsi, aCopystringw; "CopyStringW"
0x180010f54  mov     edi, 80070057h
0x180010f59  mov     rdx, rsi
0x180010f5c  lea     r8, aSource; "source"
0x180010f63  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180010f6a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180010f6f  lea     rdx, aSource; "source"
0x180010f76  mov     rcx, rsi; unsigned __int16 *
0x180010f79  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180010f7e  jmp     loc_180010E68
0x180010f83  lea     rdx, aCopystringw; "CopyStringW"
0x180010f8a  mov     edi, 8007000Eh
0x180010f8f  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x180010f96  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180010f9b  jmp     loc_180010E68
```
