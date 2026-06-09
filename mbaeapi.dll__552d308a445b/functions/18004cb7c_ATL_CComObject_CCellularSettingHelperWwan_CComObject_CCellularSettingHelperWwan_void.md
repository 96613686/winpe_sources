# ATL::CComObject<CCellularSettingHelperWwan>::~CComObject<CCellularSettingHelperWwan>(void)

- ea: `0x18004cb7c`
- end: `0x18004cbef`
- name: `??1?$CComObject@VCCellularSettingHelperWwan@@@ATL@@UEAA@XZ`
- size: `115`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004cfe0`

## callees

- `0x18004cb7c`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004cbad`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004cbe3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004cbad`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004cbe3`

## pseudocode

```c
void __fastcall ATL::CComObject<CCellularSettingHelperWwan>::~CComObject<CCellularSettingHelperWwan>(__int64 a1)
{
  volatile signed __int32 *v2; // rcx

  *(_DWORD *)(a1 + 88) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CCellularSettingHelperWwan>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v2 = *(volatile signed __int32 **)(a1 + 40);
  if ( v2 && _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
  if ( *(_BYTE *)(a1 + 136) )
  {
    *(_BYTE *)(a1 + 136) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
  }
}

```

## disassembly

```asm
0x18004cb7c  push    rbx
0x18004cb7e  sub     rsp, 20h
0x18004cb82  mov     dword ptr [rcx+58h], 0C0000001h
0x18004cb89  lea     rax, ??_7?$CComObject@VCCellularSettingHelperWwan@@@ATL@@6B@; const ATL::CComObject<CCellularSettingHelperWwan>::`vftable'
0x18004cb90  mov     [rcx], rax
0x18004cb93  mov     rbx, rcx
0x18004cb96  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18004cb9d  mov     rax, [rcx]
0x18004cba0  mov     rax, [rax+10h]
0x18004cba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cba9  lea     rcx, [rbx+30h]; lpCriticalSection
0x18004cbad  call    cs:__imp_DeleteCriticalSection
0x18004cbb3  mov     rcx, [rbx+28h]
0x18004cbb7  test    rcx, rcx
0x18004cbba  jz      short loc_18004CBD5
0x18004cbbc  or      eax, 0FFFFFFFFh
0x18004cbbf  lock xadd [rcx+0Ch], eax
0x18004cbc4  cmp     eax, 1
0x18004cbc7  jnz     short loc_18004CBD5
0x18004cbc9  mov     rax, [rcx]
0x18004cbcc  mov     rax, [rax+8]
0x18004cbd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cbd5  lea     rcx, [rbx+60h]; lpCriticalSection
0x18004cbd9  cmp     byte ptr [rcx+28h], 0
0x18004cbdd  jz      short loc_18004CBE9
0x18004cbdf  mov     byte ptr [rcx+28h], 0
0x18004cbe3  call    cs:__imp_DeleteCriticalSection
0x18004cbe9  add     rsp, 20h
0x18004cbed  pop     rbx
0x18004cbee  retn
```
