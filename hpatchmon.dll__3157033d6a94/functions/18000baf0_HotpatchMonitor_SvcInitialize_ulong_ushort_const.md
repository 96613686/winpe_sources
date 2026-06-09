# HotpatchMonitor::SvcInitialize(ulong,ushort * * const)

- ea: `0x18000baf0`
- end: `0x18000bbc7`
- name: `?SvcInitialize@HotpatchMonitor@@MEAAJKQEAPEAG@Z`
- size: `215`
- prototype: `__int64 __fastcall(HotpatchMonitor *this, __int64, unsigned __int16 **const)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800011cc`
- `0x180002270`
- `0x18000baf0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb2f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000bb18`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000bb18`

## pseudocode

```c
__int64 __fastcall HotpatchMonitor::SvcInitialize(HotpatchMonitor *this, __int64 a2, unsigned __int16 **const a3)
{
  HANDLE EventW; // rax
  unsigned int v5; // ebx
  signed int LastError; // eax
  unsigned int v8; // [rsp+30h] [rbp-48h] BYREF
  char v9[32]; // [rsp+38h] [rbp-40h] BYREF
  unsigned int *v10; // [rsp+58h] [rbp-20h]
  __int64 v11; // [rsp+60h] [rbp-18h]

  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 6) = EventW;
  if ( !EventW || (v5 = 0, EventW == (HANDLE)-1LL) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_18001E048 > 5 )
    {
      v8 = v5;
      v10 = &v8;
      v11 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, qword_180019178, 0, 0, 3, v9);
    }
    (*(void (__fastcall **)(HotpatchMonitor *, __int64, _QWORD))(*(_QWORD *)this + 32LL))(this, 1, 0);
  }
  return v5;
}

```

## disassembly

```asm
0x18000baf0  mov     [rsp+arg_8], rbx
0x18000baf5  push    rdi
0x18000baf6  sub     rsp, 70h
0x18000bafa  mov     rax, cs:__security_cookie
0x18000bb01  xor     rax, rsp
0x18000bb04  mov     [rsp+78h+var_10], rax
0x18000bb09  xor     r9d, r9d; lpName
0x18000bb0c  mov     rdi, rcx
0x18000bb0f  xor     r8d, r8d; bInitialState
0x18000bb12  xor     ecx, ecx; lpEventAttributes
0x18000bb14  lea     edx, [r9+1]; bManualReset
0x18000bb18  call    cs:__imp_CreateEventW
0x18000bb1e  mov     [rdi+30h], rax
0x18000bb22  test    rax, rax
0x18000bb25  jz      short loc_18000BB2F
0x18000bb27  xor     ebx, ebx
0x18000bb29  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000bb2d  jnz     short loc_18000BBAA
0x18000bb2f  call    cs:__imp_GetLastError
0x18000bb35  mov     ebx, eax
0x18000bb37  test    eax, eax
0x18000bb39  jle     short loc_18000BB44
0x18000bb3b  movzx   ebx, ax
0x18000bb3e  or      ebx, 80070000h
0x18000bb44  mov     eax, cs:dword_18001E048
0x18000bb4a  cmp     eax, 5
0x18000bb4d  jbe     short loc_18000BB91
0x18000bb4f  lea     rax, [rsp+78h+var_48]
0x18000bb54  mov     [rsp+78h+var_48], ebx
0x18000bb58  mov     [rsp+78h+var_20], rax
0x18000bb5d  lea     rdx, qword_180019178
0x18000bb64  lea     rax, [rsp+78h+var_40]
0x18000bb69  mov     [rsp+78h+var_18], 4
0x18000bb72  mov     [rsp+78h+var_50], rax
0x18000bb77  lea     rcx, dword_18001E048
0x18000bb7e  xor     r9d, r9d
0x18000bb81  mov     [rsp+78h+var_58], 3
0x18000bb89  xor     r8d, r8d
0x18000bb8c  call    _tlgWriteTransfer_EventWriteTransfer
0x18000bb91  mov     r8, [rdi]
0x18000bb94  xor     r9d, r9d
0x18000bb97  mov     rcx, rdi
0x18000bb9a  mov     rax, [r8+20h]
0x18000bb9e  lea     edx, [r9+1]
0x18000bba2  xor     r8d, r8d
0x18000bba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbaa  mov     eax, ebx
0x18000bbac  mov     rcx, [rsp+78h+var_10]
0x18000bbb1  xor     rcx, rsp; StackCookie
0x18000bbb4  call    __security_check_cookie
0x18000bbb9  mov     rbx, [rsp+78h+arg_8]
0x18000bbc1  add     rsp, 70h
0x18000bbc5  pop     rdi
0x18000bbc6  retn
```
