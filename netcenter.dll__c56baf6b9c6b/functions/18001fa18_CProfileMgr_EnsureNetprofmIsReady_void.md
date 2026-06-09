# CProfileMgr::EnsureNetprofmIsReady(void)

- ea: `0x18001fa18`
- end: `0x18001fad1`
- name: `?EnsureNetprofmIsReady@CProfileMgr@@QEAAJXZ`
- size: `185`
- prototype: `__int64 __fastcall(CProfileMgr *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001f550`
- `0x180020cf8`

## callees

- `0x180007e50`
- `0x180014274`
- `0x18001fa18`
- `0x180023010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18001fa71`
- `KERNEL32!Sleep` at `0x18001fa71`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProfileMgr::EnsureNetprofmIsReady(CProfileMgr *this)
{
  unsigned int v3; // ebx
  DWORD v4; // esi
  int i; // edi
  __int64 v6; // [rsp+50h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 4) )
    return 2147942487LL;
  v3 = 0;
  v4 = 1000;
  for ( i = 0; i < 9; ++i )
  {
    v6 = 0;
    v3 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**((_QWORD **)this + 4) + 32LL))(
           *((_QWORD *)this + 4),
           1,
           &v6);
    if ( v3 != -2147483638 )
    {
      ATL::CComPtrBase<IShellFolder2>::~CComPtrBase<IShellFolder2>(&v6);
      break;
    }
    Sleep(v4);
    v4 += 1000;
    ATL::CComPtrBase<IShellFolder2>::~CComPtrBase<IShellFolder2>(&v6);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_edb4701937c33b484ee7d731345f6be9_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18001fa18  push    rbx
0x18001fa1a  push    rbp
0x18001fa1b  push    rsi
0x18001fa1c  push    rdi
0x18001fa1d  sub     rsp, 28h
0x18001fa21  mov     rbp, rcx
0x18001fa24  cmp     qword ptr [rcx+20h], 0
0x18001fa29  jnz     short loc_18001FA35
0x18001fa2b  mov     eax, 80070057h
0x18001fa30  jmp     loc_18001FAC8
0x18001fa35  xor     ebx, ebx
0x18001fa37  mov     esi, 3E8h
0x18001fa3c  xor     edi, edi
0x18001fa3e  cmp     edi, 9
0x18001fa41  jge     short loc_18001FA95
0x18001fa43  mov     [rsp+48h+arg_0], 0
0x18001fa4c  mov     rcx, [rbp+20h]
0x18001fa50  mov     rax, [rcx]
0x18001fa53  lea     r8, [rsp+48h+arg_0]
0x18001fa58  mov     edx, 1
0x18001fa5d  mov     rax, [rax+20h]
0x18001fa61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa66  mov     ebx, eax
0x18001fa68  cmp     eax, 8000000Ah
0x18001fa6d  jnz     short loc_18001FA8B
0x18001fa6f  mov     ecx, esi; dwMilliseconds
0x18001fa71  call    cs:__imp_Sleep
0x18001fa77  add     esi, 3E8h
0x18001fa7d  lea     rcx, [rsp+48h+arg_0]
0x18001fa82  call    ??1?$CComPtrBase@UIShellFolder2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IShellFolder2>::~CComPtrBase<IShellFolder2>(void)
0x18001fa87  inc     edi
0x18001fa89  jmp     short loc_18001FA3E
0x18001fa8b  lea     rcx, [rsp+48h+arg_0]
0x18001fa90  call    ??1?$CComPtrBase@UIShellFolder2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IShellFolder2>::~CComPtrBase<IShellFolder2>(void)
0x18001fa95  lea     rax, WPP_GLOBAL_Control
0x18001fa9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001faa3  cmp     rcx, rax
0x18001faa6  jz      short loc_18001FAC6
0x18001faa8  test    byte ptr [rcx+1Ch], 8
0x18001faac  jz      short loc_18001FAC6
0x18001faae  mov     edx, 27h ; '''
0x18001fab3  mov     r9d, ebx
0x18001fab6  lea     r8, WPP_edb4701937c33b484ee7d731345f6be9_Traceguids
0x18001fabd  mov     rcx, [rcx+10h]
0x18001fac1  call    WPP_SF_d
0x18001fac6  mov     eax, ebx
0x18001fac8  add     rsp, 28h
0x18001facc  pop     rdi
0x18001facd  pop     rsi
0x18001face  pop     rbp
0x18001facf  pop     rbx
0x18001fad0  retn
```
