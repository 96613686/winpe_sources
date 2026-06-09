# wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)

- ea: `0x180008138`
- end: `0x180008207`
- name: `??0?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z`
- size: `207`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000e750`

## callees

- `0x180006e9c`

## string_xrefs

- `0x180008170`: `TryLookupExtensionPointImplementationAcid`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1)
{
  __int64 v2; // rbx

  *(_QWORD *)a1 = &wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable';
  v2 = a1 + 8;
  *(_DWORD *)(a1 + 8) = 0;
  *(_BYTE *)(a1 + 12) = 0;
  *(_BYTE *)(a1 + 72) = 0;
  *(_DWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = "TryLookupExtensionPointImplementationAcid";
  *(_QWORD *)(a1 + 64) = 0;
  *(_DWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 240) = 0;
  *(_QWORD *)(a1 + 248) = 0;
  memset_0((void *)(a1 + 88), 0, 0x98u);
  *(_DWORD *)(v2 + 248) = 1;
  *(_QWORD *)(v2 + 256) = 0;
  *(_QWORD *)(a1 + 272) = v2;
  *(_QWORD *)(a1 + 280) = 0;
  *(_QWORD *)(a1 + 288) = 0;
  *(_QWORD *)(a1 + 296) = a1;
  *(_QWORD *)(a1 + 304) = 0;
  *(_DWORD *)(a1 + 312) = 0;
  *(_QWORD *)(a1 + 320) = a1 + 48;
  *(_BYTE *)(a1 + 328) = 0;
  return a1;
}

```

## disassembly

```asm
0x180008138  mov     r11, rsp
0x18000813b  mov     [r11+10h], rbx
0x18000813f  mov     [r11+18h], rsi
0x180008143  mov     [r11+8], rcx
0x180008147  push    rdi
0x180008148  sub     rsp, 30h
0x18000814c  mov     rdi, rcx
0x18000814f  lea     rax, ??_7?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x180008156  mov     [rcx], rax
0x180008159  lea     rbx, [rcx+8]
0x18000815d  mov     [r11+20h], rbx
0x180008161  xor     esi, esi
0x180008163  mov     [rbx], esi
0x180008165  mov     [rbx+4], sil
0x180008169  mov     [rbx+40h], sil
0x18000816d  mov     [rbx+28h], esi
0x180008170  lea     rax, aTrylookupexten; "TryLookupExtensionPointImplementationAc"...
0x180008177  mov     [rbx+30h], rax
0x18000817b  mov     [rbx+38h], rsi
0x18000817f  mov     [rbx+48h], esi
0x180008182  lea     rcx, [rbx+50h]; void *
0x180008186  mov     [r11-18h], rcx
0x18000818a  mov     [rcx+98h], rsi
0x180008191  mov     [rcx+0A0h], rsi
0x180008198  xor     edx, edx; Val
0x18000819a  mov     r8d, 98h; Size
0x1800081a0  call    memset_0
0x1800081a5  nop
0x1800081a6  mov     dword ptr [rbx+0F8h], 1
0x1800081b0  xor     eax, eax
0x1800081b2  mov     [rbx+100h], rax
0x1800081b9  mov     [rdi+110h], rbx
0x1800081c0  mov     [rdi+118h], rsi
0x1800081c7  mov     [rdi+120h], rsi
0x1800081ce  mov     [rdi+128h], rdi
0x1800081d5  mov     [rdi+130h], rsi
0x1800081dc  mov     [rdi+138h], esi
0x1800081e2  lea     rax, [rdi+30h]
0x1800081e6  mov     [rdi+140h], rax
0x1800081ed  mov     [rdi+148h], sil
0x1800081f4  mov     rax, rdi
0x1800081f7  mov     rbx, [rsp+38h+arg_8]
0x1800081fc  mov     rsi, [rsp+38h+arg_10]
0x180008201  add     rsp, 30h
0x180008205  pop     rdi
0x180008206  retn
```
