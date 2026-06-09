# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IInitializeWithStream,IThumbnailProvider,IPreviewHandler,IPreviewHandlerVisuals,IOleWindow,IObjectWithSite>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800041a0`
- end: `0x18000423d`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIInitializeWithStream@@UIThumbnailProvider@@UIPreviewHandler@@UIPreviewHandlerVisuals@@UIOleWindow@@UIObjectWithSite@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `157`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004250`
- `0x180004260`
- `0x180004270`
- `0x180004280`
- `0x180004290`

## callees

- `0x180003a00`
- `0x1800041a0`
- `0x18000b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IInitializeWithStream,IThumbnailProvider,IPreviewHandler,IPreviewHandlerVisuals,IOleWindow,IObjectWithSite>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  int CanCastTo; // ebx

  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 == -1205554019
      && a2[1] == *(_DWORD *)&GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f.Data2
      && a2[2] == *(_DWORD *)GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f.Data4
      && a2[3] == *(_DWORD *)&GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f.Data4[4] )
    {
      *a3 = a1;
      CanCastTo = 0;
      goto LABEL_12;
    }
LABEL_11:
    CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IThumbnailProvider,IPreviewHandler,IPreviewHandlerVisuals,IOleWindow,IObjectWithSite>::CanCastTo(a1 + 8);
    if ( CanCastTo < 0 )
      return (unsigned int)CanCastTo;
LABEL_12:
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
    return (unsigned int)CanCastTo;
  }
  if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
    || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
    || a2[3] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
  {
    goto LABEL_11;
  }
  *a3 = a1;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x1800041a0  push    rbx
0x1800041a2  sub     rsp, 20h
0x1800041a6  mov     qword ptr [r8], 0
0x1800041ad  cmp     dword ptr [rdx], 0
0x1800041b0  jnz     short loc_1800041E6
0x1800041b2  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x1800041b8  cmp     [rdx+4], eax
0x1800041bb  jnz     short loc_180004216
0x1800041bd  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x1800041c3  cmp     [rdx+8], eax
0x1800041c6  jnz     short loc_180004216
0x1800041c8  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x1800041ce  cmp     [rdx+0Ch], eax
0x1800041d1  jnz     short loc_180004216
0x1800041d3  mov     [r8], rcx
0x1800041d6  mov     rax, [rcx]
0x1800041d9  mov     rax, [rax+8]
0x1800041dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041e2  xor     ebx, ebx
0x1800041e4  jmp     short loc_180004235
0x1800041e6  cmp     dword ptr [rdx], 0B824B49Dh
0x1800041ec  jnz     short loc_180004216
0x1800041ee  mov     eax, dword ptr cs:_GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f.Data2
0x1800041f4  cmp     [rdx+4], eax
0x1800041f7  jnz     short loc_180004216
0x1800041f9  mov     eax, dword ptr cs:_GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f.Data4
0x1800041ff  cmp     [rdx+8], eax
0x180004202  jnz     short loc_180004216
0x180004204  mov     eax, dword ptr cs:_GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f.Data4+4
0x18000420a  cmp     [rdx+0Ch], eax
0x18000420d  jnz     short loc_180004216
0x18000420f  mov     [r8], rcx
0x180004212  xor     ebx, ebx
0x180004214  jmp     short loc_180004225
0x180004216  add     rcx, 8
0x18000421a  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIThumbnailProvider@@UIPreviewHandler@@UIPreviewHandlerVisuals@@UIOleWindow@@UIObjectWithSite@@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IThumbnailProvider,IPreviewHandler,IPreviewHandlerVisuals,IOleWindow,IObjectWithSite>::CanCastTo(_GUID const &,void * *,bool *)
0x18000421f  mov     ebx, eax
0x180004221  test    eax, eax
0x180004223  js      short loc_180004235
0x180004225  mov     rcx, [r8]
0x180004228  mov     rdx, [rcx]
0x18000422b  mov     rax, [rdx+8]
0x18000422f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004234  nop
0x180004235  mov     eax, ebx
0x180004237  add     rsp, 20h
0x18000423b  pop     rbx
0x18000423c  retn
```
