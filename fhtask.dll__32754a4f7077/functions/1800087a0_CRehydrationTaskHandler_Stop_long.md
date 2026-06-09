# CRehydrationTaskHandler::Stop(long *)

- ea: `0x1800087a0`
- end: `0x18000886b`
- name: `?Stop@CRehydrationTaskHandler@@UEAAJPEAJ@Z`
- size: `203`
- prototype: `__int64 __fastcall(CRehydrationTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x180005ea4`
- `0x1800067a0`
- `0x1800087a0`
- `0x18000b010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180008807`
- `KERNEL32!WaitForSingleObject` at `0x180008807`
- `KERNEL32!GetLastError` at `0x180008811`
- `KERNEL32!GetLastError` at `0x180008811`

## pseudocode

```c
__int64 __fastcall CRehydrationTaskHandler::Stop(CRehydrationTaskHandler *this, int *a2)
{
  __int64 v4; // rcx
  signed int LastError; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids);
  *((_BYTE *)this + 88) = 1;
  v4 = *((_QWORD *)this + 9);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 152LL))(v4);
  if ( WaitForSingleObject(*((HANDLE *)this + 10), 0xFFFFFFFF) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids,
        (unsigned int)LastError);
  }
  if ( a2 )
    *a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x1800087a0  mov     [rsp+arg_0], rbx
0x1800087a5  mov     [rsp+arg_8], rsi
0x1800087aa  push    rdi
0x1800087ab  sub     rsp, 20h
0x1800087af  mov     rdi, rdx
0x1800087b2  mov     rbx, rcx
0x1800087b5  lea     rsi, WPP_GLOBAL_Control
0x1800087bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087c3  cmp     rcx, rsi
0x1800087c6  jz      short loc_1800087E4
0x1800087c8  test    byte ptr [rcx+1Ch], 8
0x1800087cc  jz      short loc_1800087E4
0x1800087ce  mov     edx, 3Ch ; '<'
0x1800087d3  lea     r8, WPP_8158daeccbd13eff1bb477c819869c69_Traceguids
0x1800087da  mov     rcx, [rcx+10h]
0x1800087de  call    WPP_SF_
0x1800087e3  nop
0x1800087e4  mov     byte ptr [rbx+58h], 1
0x1800087e8  mov     rcx, [rbx+48h]
0x1800087ec  test    rcx, rcx
0x1800087ef  jz      short loc_180008800
0x1800087f1  mov     rax, [rcx]
0x1800087f4  mov     rax, [rax+98h]
0x1800087fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008800  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008803  mov     rcx, [rbx+50h]; hHandle
0x180008807  call    cs:__imp_WaitForSingleObject
0x18000880d  test    eax, eax
0x18000880f  jz      short loc_18000884E
0x180008811  call    cs:__imp_GetLastError
0x180008817  test    eax, eax
0x180008819  jle     short loc_180008823
0x18000881b  movzx   eax, ax
0x18000881e  or      eax, 80070000h
0x180008823  mov     rcx, cs:WPP_GLOBAL_Control
0x18000882a  cmp     rcx, rsi
0x18000882d  jz      short loc_18000884E
0x18000882f  test    byte ptr [rcx+1Ch], 1
0x180008833  jz      short loc_18000884E
0x180008835  mov     edx, 3Fh ; '?'
0x18000883a  mov     r9d, eax
0x18000883d  lea     r8, WPP_8158daeccbd13eff1bb477c819869c69_Traceguids
0x180008844  mov     rcx, [rcx+10h]
0x180008848  call    WPP_SF_d
0x18000884d  nop
0x18000884e  test    rdi, rdi
0x180008851  jz      short loc_180008859
0x180008853  mov     dword ptr [rdi], 0
0x180008859  xor     eax, eax
0x18000885b  mov     rbx, [rsp+28h+arg_0]
0x180008860  mov     rsi, [rsp+28h+arg_8]
0x180008865  add     rsp, 20h
0x180008869  pop     rdi
0x18000886a  retn
```
