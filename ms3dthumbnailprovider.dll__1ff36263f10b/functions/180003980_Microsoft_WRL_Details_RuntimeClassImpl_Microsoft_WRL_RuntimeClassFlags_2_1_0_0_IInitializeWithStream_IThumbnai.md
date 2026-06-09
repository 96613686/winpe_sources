# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IInitializeWithStream,IThumbnailProvider,IPreviewHandler,IPreviewHandlerVisuals,IOleWindow,IObjectWithSite>::AddRef(void)

- ea: `0x180003980`
- end: `0x1800039a9`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIInitializeWithStream@@UIThumbnailProvider@@UIPreviewHandler@@UIPreviewHandlerVisuals@@UIOleWindow@@UIObjectWithSite@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800039b0`
- `0x1800039c0`
- `0x1800039d0`
- `0x1800039e0`
- `0x1800039f0`

## callees

- `0x180003980`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IInitializeWithStream,IThumbnailProvider,IPreviewHandler,IPreviewHandlerVisuals,IOleWindow,IObjectWithSite>::AddRef(
        __int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 52);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 52), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x180003980  mov     r9d, 7FFFFFFFh
0x180003986  jmp     short loc_180003996
0x180003988  lea     edx, [r8+1]
0x18000398c  mov     eax, r8d
0x18000398f  lock cmpxchg [rcx+34h], edx
0x180003994  jz      short loc_1800039A1
0x180003996  mov     r8d, [rcx+34h]
0x18000399a  cmp     r8d, r9d
0x18000399d  jnz     short loc_180003988
0x18000399f  jmp     short loc_1800039A5
0x1800039a1  lea     r9d, [r8+1]
0x1800039a5  mov     eax, r9d
0x1800039a8  retn
```
