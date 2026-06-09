# DrDeviceManager::FindDeviceByDosName(uchar *,SmartPtr<DrDevice> &,int)

- ea: `0x1400268e0`
- end: `0x140026a40`
- name: `?FindDeviceByDosName@DrDeviceManager@@QEAAHPEAEAEAV?$SmartPtr@VDrDevice@@@@H@Z`
- size: `352`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `8`
- tags: ``

## callers

- `0x140001350`
- `0x140020100`
- `0x140025c40`
- `0x140026380`
- `0x140026c18`
- `0x140027fe0`

## callees

- `0x140001660`
- `0x140001890`
- `0x140001c50`
- `0x140001ef0`
- `0x14000324c`
- `0x140005be8`
- `0x140006560`
- `0x1400268e0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140026917`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140026917`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140026929`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140026929`
- `ntoskrnl!_stricmp` at `0x140026964`
- `ntoskrnl!_stricmp` at `0x140026964`

## pseudocode

```c
_BOOL8 __fastcall DrDeviceManager::FindDeviceByDosName(__int64 a1, const char *a2, RefCount **a3)
{
  struct ListEntry *i; // rax
  struct ListEntry *v7; // rbx
  RefCount *v8; // rdi
  const char *v9; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_sd(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a2);
  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite((PERESOURCE)(a1 + 80), 1u);
  for ( i = DoubleList::First((DoubleList *)(a1 + 32)); ; i = DoubleList::Next((DoubleList *)(a1 + 32), v7) )
  {
    v7 = i;
    if ( !i )
      break;
    v8 = (RefCount *)*((_QWORD *)i + 2);
    v9 = (const char *)(*(__int64 (__fastcall **)(RefCount *))(*(_QWORD *)v8 + 104LL))(v8);
    if ( !_stricmp(v9, a2) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x2Eu,
          (__int64)WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids);
      if ( (*(unsigned int (__fastcall **)(RefCount *))(*(_QWORD *)v8 + 96LL))(v8) )
      {
        if ( *a3 )
          RefCount::Release(*a3);
        *a3 = v8;
        RefCount::AddRef(v8);
      }
      break;
    }
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(a1 + 64) + 32LL))(a1 + 64);
  return *a3 != 0;
}

```

## disassembly

```asm
0x1400268e0  mov     [rsp+arg_8], rbx
0x1400268e5  mov     [rsp+arg_10], rbp
0x1400268ea  push    rsi
0x1400268eb  push    r12
0x1400268ed  push    r13
0x1400268ef  push    r14
0x1400268f1  push    r15
0x1400268f3  sub     rsp, 30h
0x1400268f7  mov     r12, r8
0x1400268fa  mov     rbp, rdx
0x1400268fd  mov     r14, rcx
0x140026900  mov     rcx, cs:WPP_GLOBAL_Control
0x140026907  lea     r13, WPP_GLOBAL_Control
0x14002690e  cmp     rcx, r13
0x140026911  jnz     loc_1400269E0
0x140026917  call    cs:__imp_KeEnterCriticalRegion
0x14002691e  nop     dword ptr [rax+rax+00h]
0x140026923  lea     rcx, [r14+50h]; Resource
0x140026927  mov     dl, 1; Wait
0x140026929  call    cs:__imp_ExAcquireResourceSharedLite
0x140026930  nop     dword ptr [rax+rax+00h]
0x140026935  lea     rcx, [r14+20h]; this
0x140026939  call    ?First@DoubleList@@QEAAPEAVListEntry@@XZ; DoubleList::First(void)
0x14002693e  mov     [rsp+58h+arg_0], rdi
0x140026943  mov     rbx, rax
0x140026946  test    rax, rax
0x140026949  jz      short loc_140026997
0x14002694b  mov     rdi, [rax+10h]
0x14002694f  mov     rcx, rdi
0x140026952  mov     rax, [rdi]
0x140026955  mov     rax, [rax+68h]
0x140026959  call    _guard_dispatch_icall
0x14002695e  mov     rcx, rax; Str1
0x140026961  mov     rdx, rbp; Str2
0x140026964  call    cs:__imp__stricmp
0x14002696b  nop     dword ptr [rax+rax+00h]
0x140026970  test    eax, eax
0x140026972  jnz     short loc_1400269CF
0x140026974  mov     rcx, cs:WPP_GLOBAL_Control
0x14002697b  cmp     rcx, r13
0x14002697e  jnz     short loc_1400269FB
0x140026980  mov     rax, [rdi]
0x140026983  mov     rcx, rdi
0x140026986  mov     rax, [rax+60h]
0x14002698a  call    _guard_dispatch_icall
0x14002698f  test    eax, eax
0x140026991  jnz     loc_140026A1F
0x140026997  mov     rax, [r14+40h]
0x14002699b  lea     rcx, [r14+40h]
0x14002699f  mov     rax, [rax+20h]
0x1400269a3  call    _guard_dispatch_icall
0x1400269a8  mov     rdi, [rsp+58h+arg_0]
0x1400269ad  xor     eax, eax
0x1400269af  cmp     [r12], rax
0x1400269b3  mov     rbx, [rsp+58h+arg_8]
0x1400269b8  mov     rbp, [rsp+58h+arg_10]
0x1400269bd  setnz   al
0x1400269c0  add     rsp, 30h
0x1400269c4  pop     r15
0x1400269c6  pop     r14
0x1400269c8  pop     r13
0x1400269ca  pop     r12
0x1400269cc  pop     rsi
0x1400269cd  retn
0x1400269cf  mov     rdx, rbx; struct ListEntry *
0x1400269d2  lea     rcx, [r14+20h]; this
0x1400269d6  call    ?Next@DoubleList@@QEAAPEAVListEntry@@PEAV2@@Z; DoubleList::Next(ListEntry *)
0x1400269db  jmp     loc_140026943
0x1400269e0  cmp     byte ptr [rcx+29h], 4
0x1400269e4  jb      loc_140026917
0x1400269ea  mov     rcx, [rcx+18h]
0x1400269ee  mov     r9, rbp
0x1400269f1  call    WPP_SF_sd
0x1400269f6  jmp     loc_140026917
0x1400269fb  cmp     byte ptr [rcx+29h], 5
0x1400269ff  jb      loc_140026980
0x140026a05  mov     rcx, [rcx+18h]
0x140026a09  lea     r8, WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids
0x140026a10  mov     edx, 2Eh ; '.'
0x140026a15  call    WPP_SF_
0x140026a1a  jmp     loc_140026980
0x140026a1f  mov     rcx, [r12]; this
0x140026a23  test    rcx, rcx
0x140026a26  jnz     short loc_140026A39
0x140026a28  mov     rcx, rdi; this
0x140026a2b  mov     [r12], rdi
0x140026a2f  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140026a34  jmp     loc_140026997
0x140026a39  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140026a3e  jmp     short loc_140026A28
```
