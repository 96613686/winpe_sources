# DllMain

- ea: `0x180011df0`
- end: `0x180011f8a`
- name: `DllMain`
- size: `410`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001618`

## callees

- `0x180011df0`
- `0x180012004`
- `0x180012aa8`

## import_xrefs

- `ntdll!EtwUnregisterTraceGuids` at `0x180011f33`
- `ntdll!EtwUnregisterTraceGuids` at `0x180011f33`
- `WppRecorderUM!WppAutoLogStop` at `0x180011f55`
- `WppRecorderUM!WppAutoLogStop` at `0x180011f55`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  char v3; // dl
  _QWORD *v4; // rbx
  __int64 v5; // rcx

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      qword_180046ED0 = 0;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_BthServTraceGuid;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      WPP_MAIN_CB = 0;
      qword_180046ED8 = 1;
      qword_180046EE8 = 0;
      dword_180046EF0 = 0;
      WppInitUm();
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v3 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
        v3 = 0;
      if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v3,
          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (LOBYTE(fdwReason) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
    {
      LOBYTE(fdwReason) = 0;
    }
    LOBYTE(lpvReserved) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)fdwReason || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        fdwReason,
        (_BYTE)lpvReserved,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control )
    {
      if ( v4 )
      {
        do
        {
          v5 = v4[1];
          if ( v5 )
          {
            EtwUnregisterTraceGuids(v5, *(_QWORD *)&fdwReason, lpvReserved);
            v4[1] = 0;
          }
          v4 = (_QWORD *)*v4;
        }
        while ( v4 );
        v4 = WPP_GLOBAL_Control;
      }
      WppAutoLogStop(v4, *(_QWORD *)&fdwReason, lpvReserved);
      WPP_RECORDER_INITIALIZED = &WPP_RECORDER_INITIALIZED;
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180011df0  mov     [rsp+arg_0], rbx
0x180011df5  mov     [rsp+arg_8], rbp
0x180011dfa  mov     [rsp+arg_10], rsi
0x180011dff  push    rdi
0x180011e00  sub     rsp, 50h
0x180011e04  xor     ebp, ebp
0x180011e06  test    edx, edx
0x180011e08  jz      loc_180011EC0
0x180011e0e  cmp     edx, 1
0x180011e11  jnz     loc_180011F6F
0x180011e17  lea     rax, WPP_ThisDir_CTLGUID_BthServTraceGuid
0x180011e1e  mov     cs:qword_180046ED0, rbp
0x180011e25  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180011e2c  lea     rax, WPP_MAIN_CB
0x180011e33  mov     cs:WPP_GLOBAL_Control, rax
0x180011e3a  mov     cs:WPP_MAIN_CB, rbp
0x180011e41  mov     cs:qword_180046ED8, 1
0x180011e4c  mov     cs:qword_180046EE8, rbp
0x180011e53  mov     cs:dword_180046EF0, ebp
0x180011e59  call    WppInitUm
0x180011e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e65  lea     rdi, WPP_GLOBAL_Control
0x180011e6c  cmp     rcx, rdi
0x180011e6f  jz      short loc_180011E79
0x180011e71  cmp     byte ptr [rcx+19h], 5
0x180011e75  mov     dl, 1
0x180011e77  jnb     short loc_180011E7C
0x180011e79  mov     dl, bpl
0x180011e7c  lea     rsi, WPP_RECORDER_INITIALIZED
0x180011e83  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180011e8a  setnz   r8b
0x180011e8e  test    dl, dl
0x180011e90  jnz     short loc_180011E9B
0x180011e92  test    r8b, r8b
0x180011e95  jz      loc_180011F6F
0x180011e9b  mov     r9, [rcx+28h]
0x180011e9f  lea     rax, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x180011ea6  mov     rcx, [rcx+10h]
0x180011eaa  mov     [rsp+58h+var_20], rax
0x180011eaf  mov     [rsp+58h+var_28], 0Ah
0x180011eb6  call    WPP_RECORDER_AND_TRACE_SF_s
0x180011ebb  jmp     loc_180011F6F
0x180011ec0  mov     rbx, cs:WPP_GLOBAL_Control
0x180011ec7  lea     rdi, WPP_GLOBAL_Control
0x180011ece  cmp     rbx, rdi
0x180011ed1  jz      short loc_180011EDB
0x180011ed3  cmp     byte ptr [rbx+19h], 5
0x180011ed7  mov     dl, 1
0x180011ed9  jnb     short loc_180011EDE
0x180011edb  mov     dl, bpl
0x180011ede  lea     rsi, WPP_RECORDER_INITIALIZED
0x180011ee5  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180011eec  setnz   r8b
0x180011ef0  test    dl, dl
0x180011ef2  jnz     short loc_180011EF9
0x180011ef4  test    r8b, r8b
0x180011ef7  jz      short loc_180011F20
0x180011ef9  mov     r9, [rbx+28h]
0x180011efd  lea     rax, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x180011f04  mov     rcx, [rbx+10h]
0x180011f08  mov     [rsp+58h+var_20], rax
0x180011f0d  mov     [rsp+58h+var_28], 0Bh
0x180011f14  call    WPP_RECORDER_AND_TRACE_SF_s
0x180011f19  mov     rbx, cs:WPP_GLOBAL_Control
0x180011f20  cmp     rbx, rdi
0x180011f23  jz      short loc_180011F6F
0x180011f25  test    rbx, rbx
0x180011f28  jz      short loc_180011F52
0x180011f2a  mov     rcx, [rbx+8]
0x180011f2e  test    rcx, rcx
0x180011f31  jz      short loc_180011F43
0x180011f33  call    cs:__imp_EtwUnregisterTraceGuids
0x180011f3a  nop     dword ptr [rax+rax+00h]
0x180011f3f  mov     [rbx+8], rbp
0x180011f43  mov     rbx, [rbx]
0x180011f46  test    rbx, rbx
0x180011f49  jnz     short loc_180011F2A
0x180011f4b  mov     rbx, cs:WPP_GLOBAL_Control
0x180011f52  mov     rcx, rbx
0x180011f55  call    cs:__imp_WppAutoLogStop
0x180011f5c  nop     dword ptr [rax+rax+00h]
0x180011f61  mov     cs:WPP_RECORDER_INITIALIZED, rsi
0x180011f68  mov     cs:WPP_GLOBAL_Control, rdi
0x180011f6f  mov     rbx, [rsp+58h+arg_0]
0x180011f74  mov     eax, 1
0x180011f79  mov     rbp, [rsp+58h+arg_8]
0x180011f7e  mov     rsi, [rsp+58h+arg_10]
0x180011f83  add     rsp, 50h
0x180011f87  pop     rdi
0x180011f88  retn
```
