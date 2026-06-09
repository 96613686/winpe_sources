# HbpEvtpFlushEventLog

- ea: `0x14001396c`
- end: `0x140013a59`
- name: `HbpEvtpFlushEventLog`
- size: `237`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140012170`
- `0x1400137b0`

## callees

- `0x140001230`
- `0x1400020f8`
- `0x140002ae0`
- `0x14001396c`

## import_xrefs

- `winhvr!WinHvFlushEventLogBuffer` at `0x1400139c5`
- `winhvr!WinHvFlushEventLogBuffer` at `0x1400139e2`
- `winhvr!WinHvFlushEventLogBuffer` at `0x1400139c5`
- `winhvr!WinHvFlushEventLogBuffer` at `0x1400139e2`

## pseudocode

```c
__int64 __fastcall HbpEvtpFlushEventLog(unsigned int a1)
{
  int v2; // edx
  __int64 *v3; // rbx
  unsigned int v4; // edi
  int v5; // eax
  int LogConfiguration; // [rsp+20h] [rbp-38h] BYREF
  __int64 *v8; // [rsp+28h] [rbp-30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-28h] BYREF

  v8 = 0;
  UserData = 0;
  LogConfiguration = HbEvtpGetLogConfiguration(a1, &v8);
  v2 = LogConfiguration;
  if ( LogConfiguration >= 0 )
  {
    v3 = v8;
    if ( *((_DWORD *)v8 + 2) && v8[4] )
    {
      if ( *((_DWORD *)v8 + 12) == 1 )
      {
        v2 = WinHvFlushEventLogBuffer(a1, 0);
        LogConfiguration = v2;
      }
      else
      {
        v4 = 0;
        do
        {
          v5 = WinHvFlushEventLogBuffer(a1, v4);
          v2 = 0;
          if ( v5 != -1070268408 )
            v2 = v5;
          if ( v2 >= 0 )
            v2 = LogConfiguration;
          else
            LogConfiguration = v2;
          ++v4;
        }
        while ( v4 < *((_DWORD *)v3 + 2) );
      }
    }
    else
    {
      v2 = -1073741811;
      LogConfiguration = -1073741811;
    }
  }
  if ( v2 < 0 )
  {
    *(_QWORD *)&UserData.Size = 4;
    UserData.Ptr = (ULONGLONG)&LogConfiguration;
    HbEvtpWriteEventLog(&HV_EVENTLOG_FLUSH_FAILED, 1u, &UserData);
    return (unsigned int)LogConfiguration;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14001396c  push    rbp
0x14001396e  push    rbx
0x14001396f  push    rsi
0x140013970  push    rdi
0x140013971  mov     rbp, rsp
0x140013974  sub     rsp, 58h
0x140013978  mov     rax, cs:__security_cookie
0x14001397f  xor     rax, rsp
0x140013982  mov     [rbp+var_18], rax
0x140013986  xorps   xmm0, xmm0
0x140013989  mov     [rbp+var_30], 0
0x140013991  lea     rdx, [rbp+var_30]
0x140013995  mov     esi, ecx
0x140013997  movups  xmmword ptr [rbp+UserData.Ptr], xmm0
0x14001399b  call    HbEvtpGetLogConfiguration
0x1400139a0  mov     [rbp+var_38], eax
0x1400139a3  mov     edx, eax
0x1400139a5  test    eax, eax
0x1400139a7  js      short loc_140013A15
0x1400139a9  mov     rbx, [rbp+var_30]
0x1400139ad  mov     eax, [rbx+8]
0x1400139b0  test    eax, eax
0x1400139b2  jz      short loc_140013A0D
0x1400139b4  cmp     qword ptr [rbx+20h], 0
0x1400139b9  jz      short loc_140013A0D
0x1400139bb  cmp     dword ptr [rbx+30h], 1
0x1400139bf  jnz     short loc_1400139D8
0x1400139c1  xor     edx, edx
0x1400139c3  mov     ecx, esi
0x1400139c5  call    cs:__imp_WinHvFlushEventLogBuffer
0x1400139cc  nop     dword ptr [rax+rax+00h]
0x1400139d1  mov     edx, eax
0x1400139d3  mov     [rbp+var_38], eax
0x1400139d6  jmp     short loc_140013A15
0x1400139d8  xor     edi, edi
0x1400139da  test    eax, eax
0x1400139dc  jz      short loc_140013A15
0x1400139de  mov     edx, edi
0x1400139e0  mov     ecx, esi
0x1400139e2  call    cs:__imp_WinHvFlushEventLogBuffer
0x1400139e9  nop     dword ptr [rax+rax+00h]
0x1400139ee  xor     edx, edx
0x1400139f0  cmp     eax, 0C0350008h
0x1400139f5  cmovnz  edx, eax
0x1400139f8  test    edx, edx
0x1400139fa  jns     short loc_140013A01
0x1400139fc  mov     [rbp+var_38], edx
0x1400139ff  jmp     short loc_140013A04
0x140013a01  mov     edx, [rbp+var_38]
0x140013a04  inc     edi
0x140013a06  cmp     edi, [rbx+8]
0x140013a09  jb      short loc_1400139DE
0x140013a0b  jmp     short loc_140013A15
0x140013a0d  mov     edx, 0C000000Dh
0x140013a12  mov     [rbp+var_38], edx
0x140013a15  test    edx, edx
0x140013a17  jns     short loc_140013A41
0x140013a19  lea     rax, [rbp+var_38]
0x140013a1d  mov     qword ptr [rbp+UserData.Size], 4
0x140013a25  lea     r8, [rbp+UserData]; UserData
0x140013a29  mov     [rbp+UserData.Ptr], rax
0x140013a2d  mov     edx, 1; UserDataCount
0x140013a32  lea     rcx, HV_EVENTLOG_FLUSH_FAILED; EventDescriptor
0x140013a39  call    HbEvtpWriteEventLog
0x140013a3e  mov     edx, [rbp+var_38]
0x140013a41  mov     eax, edx
0x140013a43  mov     rcx, [rbp+var_18]
0x140013a47  xor     rcx, rsp; StackCookie
0x140013a4a  call    __security_check_cookie
0x140013a4f  add     rsp, 58h
0x140013a53  pop     rdi
0x140013a54  pop     rsi
0x140013a55  pop     rbx
0x140013a56  pop     rbp
0x140013a57  retn
```
