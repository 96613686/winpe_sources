# CPnpxPairingHandler::~CPnpxPairingHandler(void)

- ea: `0x18000d5b0`
- end: `0x18000d69a`
- name: `??1CPnpxPairingHandler@@UEAA@XZ`
- size: `234`
- prototype: `void __fastcall(CPnpxPairingHandler *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180005410`
- `0x1800054d0`
- `0x180005550`

## callees

- `0x18000bce4`
- `0x18000d5b0`
- `0x180014010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000d602`
- `KERNEL32!CloseHandle` at `0x18000d602`
- `KERNEL32!DeleteCriticalSection` at `0x18000d689`
- `KERNEL32!DeleteCriticalSection` at `0x18000d689`

## pseudocode

```c
void __fastcall CPnpxPairingHandler::~CPnpxPairingHandler(CPnpxPairingHandler *this)
{
  _QWORD *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 14) )
  {
    CloseHandle(*((HANDLE *)this + 14));
    *((_QWORD *)this + 14) = 0;
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 4u )
    WPP_SF_sq(v2[2], 13, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids);
  v3 = *((_QWORD *)this + 12);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 11);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_QWORD *)this + 10);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( *((_BYTE *)this + 72) )
  {
    *((_BYTE *)this + 72) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  }
}

```

## disassembly

```asm
0x18000d5b0  mov     [rsp+arg_0], rbx
0x18000d5b5  push    rsi
0x18000d5b6  sub     rsp, 30h
0x18000d5ba  mov     rbx, rcx
0x18000d5bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5c4  lea     rsi, WPP_GLOBAL_Control
0x18000d5cb  cmp     rcx, rsi
0x18000d5ce  jz      short loc_18000D5F7
0x18000d5d0  cmp     byte ptr [rcx+19h], 4
0x18000d5d4  jb      short loc_18000D5F7
0x18000d5d6  mov     rcx, [rcx+10h]
0x18000d5da  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000d5e1  mov     edx, 0Ch
0x18000d5e6  mov     [rsp+38h+var_18], rbx
0x18000d5eb  call    WPP_SF_sq
0x18000d5f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5f7  cmp     qword ptr [rbx+70h], 0
0x18000d5fc  jz      short loc_18000D617
0x18000d5fe  mov     rcx, [rbx+70h]; hObject
0x18000d602  call    cs:__imp_CloseHandle
0x18000d608  mov     qword ptr [rbx+70h], 0
0x18000d610  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d617  cmp     rcx, rsi
0x18000d61a  jz      short loc_18000D63C
0x18000d61c  cmp     byte ptr [rcx+19h], 4
0x18000d620  jb      short loc_18000D63C
0x18000d622  mov     rcx, [rcx+10h]
0x18000d626  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000d62d  mov     edx, 0Dh
0x18000d632  mov     [rsp+38h+var_18], rbx
0x18000d637  call    WPP_SF_sq
0x18000d63c  mov     rcx, [rbx+60h]
0x18000d640  test    rcx, rcx
0x18000d643  jz      short loc_18000D651
0x18000d645  mov     rax, [rcx]
0x18000d648  mov     rax, [rax+10h]
0x18000d64c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d651  mov     rcx, [rbx+58h]
0x18000d655  test    rcx, rcx
0x18000d658  jz      short loc_18000D666
0x18000d65a  mov     rax, [rcx]
0x18000d65d  mov     rax, [rax+10h]
0x18000d661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d666  mov     rcx, [rbx+50h]
0x18000d66a  test    rcx, rcx
0x18000d66d  jz      short loc_18000D67B
0x18000d66f  mov     rax, [rcx]
0x18000d672  mov     rax, [rax+10h]
0x18000d676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d67b  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000d67f  cmp     byte ptr [rcx+28h], 0
0x18000d683  jz      short loc_18000D68F
0x18000d685  mov     byte ptr [rcx+28h], 0
0x18000d689  call    cs:__imp_DeleteCriticalSection
0x18000d68f  mov     rbx, [rsp+38h+arg_0]
0x18000d694  add     rsp, 30h
0x18000d698  pop     rsi
0x18000d699  retn
```
