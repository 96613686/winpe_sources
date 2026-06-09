# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IInitializeWithStream,IThumbnailProvider,IPreviewHandler,IPreviewHandlerVisuals,IOleWindow,IObjectWithSite>::Release(void)

- ea: `0x1800042a0`
- end: `0x180004301`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIInitializeWithStream@@UIThumbnailProvider@@UIPreviewHandler@@UIPreviewHandlerVisuals@@UIOleWindow@@UIObjectWithSite@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004310`
- `0x180004320`
- `0x180004330`
- `0x180004340`
- `0x180004350`

## callees

- `0x1800042a0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IInitializeWithStream,IThumbnailProvider,IPreviewHandler,IPreviewHandlerVisuals,IOleWindow,IObjectWithSite>::Release(
        volatile signed __int32 *a1)
{
  __int64 v1; // r9
  __int64 v2; // r8
  unsigned int v3; // ebx

  v1 = 0x7FFFFFFF;
  do
    v2 = *((unsigned int *)a1 + 13);
  while ( (_DWORD)v2 != 0x7FFFFFFF && (_DWORD)v2 != _InterlockedCompareExchange(a1 + 13, v2 - 1, v2) );
  v3 = v2 - 1;
  if ( (_DWORD)v2 == 1 )
  {
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64, __int64, __int64))(*(_QWORD *)a1 + 32LL))(
        a1,
        1,
        v2,
        0x7FFFFFFF);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, _QWORD, __int64, __int64))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL))(
        Microsoft::WRL::Details::ModuleBase::module_,
        *(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_,
        v2,
        v1);
  }
  return v3;
}

```

## disassembly

```asm
0x1800042a0  push    rbx
0x1800042a2  sub     rsp, 20h
0x1800042a6  mov     r9d, 7FFFFFFFh
0x1800042ac  jmp     short loc_1800042BC
0x1800042ae  lea     edx, [r8-1]
0x1800042b2  mov     eax, r8d
0x1800042b5  lock cmpxchg [rcx+34h], edx
0x1800042ba  jz      short loc_1800042C5
0x1800042bc  mov     r8d, [rcx+34h]
0x1800042c0  cmp     r8d, r9d
0x1800042c3  jnz     short loc_1800042AE
0x1800042c5  lea     ebx, [r8-1]
0x1800042c9  test    ebx, ebx
0x1800042cb  jnz     short loc_1800042F9
0x1800042cd  test    rcx, rcx
0x1800042d0  jz      short loc_1800042E1
0x1800042d2  mov     rax, [rcx]
0x1800042d5  lea     edx, [rbx+1]
0x1800042d8  mov     rax, [rax+20h]
0x1800042dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042e1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800042e8  test    rcx, rcx
0x1800042eb  jz      short loc_1800042F9
0x1800042ed  mov     rdx, [rcx]
0x1800042f0  mov     rax, [rdx+10h]
0x1800042f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042f9  mov     eax, ebx
0x1800042fb  add     rsp, 20h
0x1800042ff  pop     rbx
0x180004300  retn
```
