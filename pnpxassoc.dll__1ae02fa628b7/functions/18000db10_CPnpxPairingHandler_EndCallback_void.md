# CPnpxPairingHandler::EndCallback(void)

- ea: `0x18000db10`
- end: `0x18000dbb5`
- name: `?EndCallback@CPnpxPairingHandler@@IEAAXXZ`
- size: `165`
- prototype: `void __fastcall(CPnpxPairingHandler *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d880`
- `0x18000d9d0`
- `0x18000e340`
- `0x18000e540`
- `0x18000e6e0`
- `0x18000e870`
- `0x18000e9d0`

## callees

- `0x18000bce4`
- `0x18000db10`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000db73`
- `KERNEL32!LeaveCriticalSection` at `0x18000db73`
- `KERNEL32!EnterCriticalSection` at `0x18000db59`
- `KERNEL32!EnterCriticalSection` at `0x18000db59`
- `KERNEL32!SetEvent` at `0x18000db69`
- `KERNEL32!SetEvent` at `0x18000db69`

## pseudocode

```c
void __fastcall CPnpxPairingHandler::EndCallback(CPnpxPairingHandler *this, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v6; // r9

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x2Au, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids, a4, this);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( (*((_DWORD *)this + 26))-- == 1 )
    SetEvent(*((HANDLE *)this + 14));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x2Bu, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids, v6, this);
}

```

## disassembly

```asm
0x18000db10  mov     [rsp+arg_8], rbx
0x18000db15  mov     [rsp+arg_10], rsi
0x18000db1a  push    rdi
0x18000db1b  sub     rsp, 30h
0x18000db1f  mov     rbx, rcx
0x18000db22  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db29  lea     rsi, WPP_GLOBAL_Control
0x18000db30  cmp     rcx, rsi
0x18000db33  jz      short loc_18000DB55
0x18000db35  cmp     byte ptr [rcx+19h], 4
0x18000db39  jb      short loc_18000DB55
0x18000db3b  mov     rcx, [rcx+10h]
0x18000db3f  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000db46  mov     edx, 2Ah ; '*'
0x18000db4b  mov     [rsp+38h+var_18], rbx
0x18000db50  call    WPP_SF_sq
0x18000db55  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000db59  call    cs:__imp_EnterCriticalSection
0x18000db5f  add     dword ptr [rbx+68h], 0FFFFFFFFh
0x18000db63  jnz     short loc_18000DB6F
0x18000db65  mov     rcx, [rbx+70h]; hEvent
0x18000db69  call    cs:__imp_SetEvent
0x18000db6f  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000db73  call    cs:__imp_LeaveCriticalSection
0x18000db79  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db80  cmp     rcx, rsi
0x18000db83  jz      short loc_18000DBA5
0x18000db85  cmp     byte ptr [rcx+19h], 4
0x18000db89  jb      short loc_18000DBA5
0x18000db8b  mov     rcx, [rcx+10h]
0x18000db8f  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000db96  mov     edx, 2Bh ; '+'
0x18000db9b  mov     [rsp+38h+var_18], rbx
0x18000dba0  call    WPP_SF_sq
0x18000dba5  mov     rbx, [rsp+38h+arg_8]
0x18000dbaa  mov     rsi, [rsp+38h+arg_10]
0x18000dbaf  add     rsp, 30h
0x18000dbb3  pop     rdi
0x18000dbb4  retn
```
