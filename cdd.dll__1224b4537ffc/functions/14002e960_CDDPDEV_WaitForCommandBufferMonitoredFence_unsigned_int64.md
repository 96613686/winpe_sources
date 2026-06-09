# CDDPDEV::WaitForCommandBufferMonitoredFence(unsigned __int64)

- ea: `0x14002e960`
- end: `0x14002ea5d`
- name: `?WaitForCommandBufferMonitoredFence@CDDPDEV@@QEAAJ_K@Z`
- size: `253`
- prototype: `__int64 __fastcall(CDDPDEV *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140015764`
- `0x1400218e4`

## callees

- `0x140012dc4`
- `0x14002e784`
- `0x14002e960`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002e99a`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002ea1b`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002e99a`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002ea1b`
- `watchdog!WdLogSingleEntry0` at `0x14002e983`
- `watchdog!WdLogSingleEntry0` at `0x14002ea04`
- `watchdog!WdLogSingleEntry0` at `0x14002e983`
- `watchdog!WdLogSingleEntry0` at `0x14002ea04`

## pseudocode

```c
__int64 __fastcall CDDPDEV::WaitForCommandBufferMonitoredFence(CDDPDEV *this, unsigned __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  _QWORD *v6; // rax
  __int64 result; // rax
  unsigned int v8; // esi
  __int64 v9; // rdx
  __int64 v10; // rcx
  _QWORD *v11; // rax

  if ( *((_QWORD *)this + 1595) >= a2 )
  {
    if ( CDDPDEV::IsCommandBufferFencePending(this, a2) )
    {
      v8 = CDDPDEV::WaitForMonitoredFenceFromCpu(this, *((_DWORD *)this + 3184), a2);
      if ( CDDPDEV::IsCommandBufferFencePending(this, a2) )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 1185;
        v11 = (_QWORD *)WdLogNewEntry5_WdAssertion(v10, v9);
        v11[3] = gCddImageInfo;
        v11[4] = (unsigned int)dword_14003E570;
        v11[5] = 215857758;
        WdLogGlobalForLineNumber = 1185;
      }
      return v8;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 1175;
    v6 = (_QWORD *)WdLogNewEntry5_WdAssertion(v5, v4);
    v6[3] = gCddImageInfo;
    v6[4] = (unsigned int)dword_14003E570;
    v6[5] = 215857758;
    result = 3221225485LL;
    WdLogGlobalForLineNumber = 1175;
  }
  return result;
}

```

## disassembly

```asm
0x14002e960  mov     [rsp+arg_0], rbx
0x14002e965  mov     [rsp+arg_8], rsi
0x14002e96a  push    rdi
0x14002e96b  sub     rsp, 20h
0x14002e96f  mov     rdi, rdx
0x14002e972  mov     rbx, rcx
0x14002e975  cmp     [rcx+31D8h], rdx
0x14002e97c  jnb     short loc_14002E9D0
0x14002e97e  mov     ecx, 1
0x14002e983  call    cs:__imp_WdLogSingleEntry0
0x14002e98a  nop     dword ptr [rax+rax+00h]
0x14002e98f  mov     ebx, 497h
0x14002e994  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002e99a  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14002e9a1  nop     dword ptr [rax+rax+00h]
0x14002e9a6  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002e9ad  mov     [rax+18h], rcx
0x14002e9b1  mov     ecx, cs:dword_14003E570; this
0x14002e9b7  mov     [rax+20h], rcx
0x14002e9bb  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002e9c3  mov     eax, 0C000000Dh
0x14002e9c8  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002e9ce  jmp     short loc_14002EA4C
0x14002e9d0  call    ?IsCommandBufferFencePending@CDDPDEV@@QEAAE_K@Z; CDDPDEV::IsCommandBufferFencePending(unsigned __int64)
0x14002e9d5  test    al, al
0x14002e9d7  jnz     short loc_14002E9DD
0x14002e9d9  xor     eax, eax
0x14002e9db  jmp     short loc_14002EA4C
0x14002e9dd  mov     edx, [rbx+31C0h]; unsigned int
0x14002e9e3  mov     r8, rdi; unsigned __int64
0x14002e9e6  mov     rcx, rbx; this
0x14002e9e9  call    ?WaitForMonitoredFenceFromCpu@CDDPDEV@@QEAAJI_K@Z; CDDPDEV::WaitForMonitoredFenceFromCpu(uint,unsigned __int64)
0x14002e9ee  mov     rdx, rdi; unsigned __int64
0x14002e9f1  mov     rcx, rbx; this
0x14002e9f4  mov     esi, eax
0x14002e9f6  call    ?IsCommandBufferFencePending@CDDPDEV@@QEAAE_K@Z; CDDPDEV::IsCommandBufferFencePending(unsigned __int64)
0x14002e9fb  test    al, al
0x14002e9fd  jz      short loc_14002EA4A
0x14002e9ff  mov     ecx, 1
0x14002ea04  call    cs:__imp_WdLogSingleEntry0
0x14002ea0b  nop     dword ptr [rax+rax+00h]
0x14002ea10  mov     ebx, 4A1h
0x14002ea15  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002ea1b  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14002ea22  nop     dword ptr [rax+rax+00h]
0x14002ea27  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002ea2e  mov     [rax+18h], rcx
0x14002ea32  mov     ecx, cs:dword_14003E570
0x14002ea38  mov     [rax+20h], rcx
0x14002ea3c  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002ea44  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002ea4a  mov     eax, esi
0x14002ea4c  mov     rbx, [rsp+28h+arg_0]
0x14002ea51  mov     rsi, [rsp+28h+arg_8]
0x14002ea56  add     rsp, 20h
0x14002ea5a  pop     rdi
0x14002ea5b  retn
```
