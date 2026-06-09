# CFhService::ReportStatus(ulong,ulong,ulong,ulong)

- ea: `0x180001f20`
- end: `0x1800020ad`
- name: `?ReportStatus@CFhService@@AEAAJKKKK@Z`
- size: `397`
- prototype: `__int64 __fastcall(CFhService *this, int, int, int, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180001690`
- `0x1800017c0`
- `0x180001950`
- `0x180008180`

## callees

- `0x180001f20`
- `0x18000ca14`
- `0x18000d9e8`

## import_xrefs

- `ADVAPI32!SetServiceStatus` at `0x180002044`
- `ADVAPI32!SetServiceStatus` at `0x180002044`
- `KERNEL32!GetLastError` at `0x18000204e`
- `KERNEL32!GetLastError` at `0x18000204e`

## string_xrefs

- `0x180001f7a`: `SERVICE_STOPPED`
- `0x180001f88`: `SERVICE_START_PENDING`
- `0x180001f96`: `SERVICE_RUNNING`
- `0x180001fa2`: `SERVICE_STOP_PENDING`

## pseudocode

```c
__int64 __fastcall CFhService::ReportStatus(CFhService *this, int a2, int a3, int a4, unsigned int a5)
{
  unsigned int v8; // edi
  PVOID *v9; // rcx
  const wchar_t *v10; // r9
  __int64 v11; // rdx
  struct _SERVICE_STATUS *v12; // rdx
  __int64 v13; // r9
  int v14; // eax
  signed int LastError; // eax

  v8 = 0;
  if ( !*((_DWORD *)this + 21) )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      switch ( a2 )
      {
        case 1:
          v10 = L"SERVICE_STOPPED";
          break;
        case 2:
          v10 = L"SERVICE_START_PENDING";
          break;
        case 4:
          v10 = L"SERVICE_RUNNING";
          break;
        default:
          v10 = L"SERVICE_STOP_PENDING";
          if ( a2 != 3 )
            v10 = L"**Unsupported_State**";
          break;
      }
      WPP_SF_Sddd(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, (_DWORD)v10);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( *(_QWORD *)this )
    {
      v12 = (struct _SERVICE_STATUS *)((char *)this + 8);
      if ( *((_DWORD *)this + 3) == 1 && a2 == 1 )
      {
        if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
        {
          v11 = 47;
          v13 = 0;
LABEL_31:
          WPP_SF_d(v9[2], v11, &WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids, v13);
        }
      }
      else
      {
        v14 = 0;
        v12->dwServiceType = 32;
        *(_QWORD *)((char *)this + 20) = 0;
        *((_DWORD *)this + 3) = a2;
        *((_DWORD *)this + 7) = a4;
        if ( a2 != 2 )
          v14 = 1221;
        *((_DWORD *)this + 8) = a5;
        *((_DWORD *)this + 4) = v14;
        if ( !SetServiceStatus(*(SERVICE_STATUS_HANDLE *)this, v12) )
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 48;
            goto LABEL_30;
          }
        }
      }
    }
    else
    {
      v8 = -2147418113;
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
      {
        v11 = 46;
LABEL_30:
        v13 = v8;
        goto LABEL_31;
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180001f20  mov     [rsp+arg_10], rbx
0x180001f25  mov     [rsp+arg_18], rsi
0x180001f2a  push    rdi
0x180001f2b  push    r14
0x180001f2d  push    r15
0x180001f2f  sub     rsp, 40h
0x180001f33  xor     r15d, r15d
0x180001f36  mov     r14d, r9d
0x180001f39  mov     esi, edx
0x180001f3b  mov     rbx, rcx
0x180001f3e  mov     edi, r15d
0x180001f41  cmp     [rcx+54h], r15d
0x180001f45  jnz     loc_180002097
0x180001f4b  mov     [rsp+58h+arg_0], rbp
0x180001f50  mov     [rsp+58h+arg_8], r12
0x180001f55  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f5c  lea     r12, WPP_GLOBAL_Control
0x180001f63  mov     ebp, [rsp+58h+arg_20]
0x180001f6a  cmp     rcx, r12
0x180001f6d  jz      short loc_180001FCD
0x180001f6f  test    byte ptr [rcx+1Ch], 10h
0x180001f73  jz      short loc_180001FCD
0x180001f75  cmp     edx, 1
0x180001f78  jnz     short loc_180001F83
0x180001f7a  lea     r9, aServiceStopped; "SERVICE_STOPPED"
0x180001f81  jmp     short loc_180001FB4
0x180001f83  cmp     esi, 2
0x180001f86  jnz     short loc_180001F91
0x180001f88  lea     r9, aServiceStartPe; "SERVICE_START_PENDING"
0x180001f8f  jmp     short loc_180001FB4
0x180001f91  cmp     esi, 4
0x180001f94  jnz     short loc_180001F9F
0x180001f96  lea     r9, aServiceRunning; "SERVICE_RUNNING"
0x180001f9d  jmp     short loc_180001FB4
0x180001f9f  cmp     esi, 3
0x180001fa2  lea     r9, aServiceStopPen; "SERVICE_STOP_PENDING"
0x180001fa9  lea     rax, aUnsupportedSta; "**Unsupported_State**"
0x180001fb0  cmovnz  r9, rax
0x180001fb4  mov     rcx, [rcx+10h]
0x180001fb8  mov     [rsp+58h+var_28], ebp
0x180001fbc  mov     [rsp+58h+var_30], r14d
0x180001fc1  call    WPP_SF_Sddd
0x180001fc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180001fcd  cmp     [rbx], rdi
0x180001fd0  jnz     short loc_180001FF4
0x180001fd2  mov     edi, 8000FFFFh
0x180001fd7  cmp     rcx, r12
0x180001fda  jz      loc_18000208D
0x180001fe0  test    byte ptr [rcx+1Ch], 1
0x180001fe4  jz      loc_18000208D
0x180001fea  mov     edx, 2Eh ; '.'
0x180001fef  jmp     loc_18000207A
0x180001ff4  cmp     dword ptr [rbx+0Ch], 1
0x180001ff8  lea     rdx, [rbx+8]; lpServiceStatus
0x180001ffc  jnz     short loc_18000201C
0x180001ffe  cmp     esi, 1
0x180002001  jnz     short loc_18000201C
0x180002003  cmp     rcx, r12
0x180002006  jz      loc_18000208D
0x18000200c  test    [rcx+1Ch], sil
0x180002010  jz      short loc_18000208D
0x180002012  mov     edx, 2Fh ; '/'
0x180002017  xor     r9d, r9d
0x18000201a  jmp     short loc_18000207D
0x18000201c  mov     eax, r15d
0x18000201f  mov     dword ptr [rdx], 20h ; ' '
0x180002025  mov     ecx, 4C5h
0x18000202a  mov     [rbx+14h], r15
0x18000202e  mov     [rbx+0Ch], esi
0x180002031  cmp     esi, 2
0x180002034  mov     [rbx+1Ch], r14d
0x180002038  cmovnz  eax, ecx
0x18000203b  mov     [rbx+20h], ebp
0x18000203e  mov     [rdx+8], eax
0x180002041  mov     rcx, [rbx]; hServiceStatus
0x180002044  call    cs:__imp_SetServiceStatus
0x18000204a  test    eax, eax
0x18000204c  jnz     short loc_18000208D
0x18000204e  call    cs:__imp_GetLastError
0x180002054  mov     edi, eax
0x180002056  test    eax, eax
0x180002058  jle     short loc_180002063
0x18000205a  movzx   edi, ax
0x18000205d  or      edi, 80070000h
0x180002063  mov     rcx, cs:WPP_GLOBAL_Control
0x18000206a  cmp     rcx, r12
0x18000206d  jz      short loc_18000208D
0x18000206f  test    byte ptr [rcx+1Ch], 1
0x180002073  jz      short loc_18000208D
0x180002075  mov     edx, 30h ; '0'
0x18000207a  mov     r9d, edi
0x18000207d  mov     rcx, [rcx+10h]
0x180002081  lea     r8, WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids
0x180002088  call    WPP_SF_d
0x18000208d  mov     rbp, [rsp+58h+arg_0]
0x180002092  mov     r12, [rsp+58h+arg_8]
0x180002097  mov     rbx, [rsp+58h+arg_10]
0x18000209c  mov     eax, edi
0x18000209e  mov     rsi, [rsp+58h+arg_18]
0x1800020a3  add     rsp, 40h
0x1800020a7  pop     r15
0x1800020a9  pop     r14
0x1800020ab  pop     rdi
0x1800020ac  retn
```
