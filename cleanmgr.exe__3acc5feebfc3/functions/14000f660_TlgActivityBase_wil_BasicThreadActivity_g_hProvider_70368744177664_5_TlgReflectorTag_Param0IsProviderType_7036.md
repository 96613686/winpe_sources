# _TlgActivityBase<wil::BasicThreadActivity<g_hProvider,70368744177664,5,_TlgReflectorTag_Param0IsProviderType>,70368744177664,5>::~_TlgActivityBase<wil::BasicThreadActivity<g_hProvider,70368744177664,5,_TlgReflectorTag_Param0IsProviderType>,70368744177664,5>(void)

- ea: `0x14000f660`
- end: `0x14000f6a6`
- name: `??1?$_TlgActivityBase@V?$BasicThreadActivity@Vg_hProvider@@$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsProviderType@@@wil@@$0EAAAAAAAAAAA@$04@@IEAA@XZ`
- size: `70`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f614`
- `0x14000f788`

## callees

- `0x14000e15c`
- `0x14000f214`
- `0x14000f660`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000f67d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000f67d`

## pseudocode

```c
void __fastcall _TlgActivityBase<wil::BasicThreadActivity<g_hProvider,70368744177664,5,_TlgReflectorTag_Param0IsProviderType>,70368744177664,5>::~_TlgActivityBase<wil::BasicThreadActivity<g_hProvider,70368744177664,5,_TlgReflectorTag_Param0IsProviderType>,70368744177664,5>(
        __int64 a1)
{
  unsigned int *v2; // rax

  if ( *(_DWORD *)a1 == 1 )
  {
    if ( *(_BYTE *)(a1 + 4) )
      EventActivityIdControl(4u, (LPGUID)(a1 + 24));
    *(_DWORD *)a1 = 2;
    v2 = (unsigned int *)g_hProvider::Provider();
    _tlgWriteActivityAutoStop<70368744177664,5>(v2, a1 + 8);
  }
  *(_DWORD *)a1 = 3;
}

```

## disassembly

```asm
0x14000f660  push    rbx
0x14000f662  sub     rsp, 20h
0x14000f666  cmp     dword ptr [rcx], 1
0x14000f669  mov     rbx, rcx
0x14000f66c  jnz     short loc_14000F69A
0x14000f66e  cmp     byte ptr [rcx+4], 0
0x14000f672  jz      short loc_14000F683
0x14000f674  lea     rdx, [rcx+18h]; ActivityId
0x14000f678  mov     ecx, 4; ControlCode
0x14000f67d  call    cs:__imp_EventActivityIdControl
0x14000f683  mov     dword ptr [rbx], 2
0x14000f689  call    ?Provider@g_hProvider@@SAPEBU_tlgProvider_t@@XZ; g_hProvider::Provider(void)
0x14000f68e  lea     rdx, [rbx+8]
0x14000f692  mov     rcx, rax
0x14000f695  call    ??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)
0x14000f69a  mov     dword ptr [rbx], 3
0x14000f6a0  add     rsp, 20h
0x14000f6a4  pop     rbx
0x14000f6a5  retn
```
