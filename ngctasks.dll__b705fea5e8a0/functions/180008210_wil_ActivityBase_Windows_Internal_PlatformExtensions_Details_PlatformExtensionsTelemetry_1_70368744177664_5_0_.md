# wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)

- ea: `0x180008210`
- end: `0x1800082df`
- name: `??0?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z`
- size: `207`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007f50`

## callees

- `0x180006e9c`

## string_xrefs

- `0x180008248`: `TryActivateContractExtension`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1)
{
  __int64 v2; // rbx

  *(_QWORD *)a1 = &wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable';
  v2 = a1 + 8;
  *(_DWORD *)(a1 + 8) = 0;
  *(_BYTE *)(a1 + 12) = 0;
  *(_BYTE *)(a1 + 72) = 0;
  *(_DWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = "TryActivateContractExtension";
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
0x180008210  mov     r11, rsp
0x180008213  mov     [r11+10h], rbx
0x180008217  mov     [r11+18h], rsi
0x18000821b  mov     [r11+8], rcx
0x18000821f  push    rdi
0x180008220  sub     rsp, 30h
0x180008224  mov     rdi, rcx
0x180008227  lea     rax, ??_7?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x18000822e  mov     [rcx], rax
0x180008231  lea     rbx, [rcx+8]
0x180008235  mov     [r11+20h], rbx
0x180008239  xor     esi, esi
0x18000823b  mov     [rbx], esi
0x18000823d  mov     [rbx+4], sil
0x180008241  mov     [rbx+40h], sil
0x180008245  mov     [rbx+28h], esi
0x180008248  lea     rax, aTryactivatecon; "TryActivateContractExtension"
0x18000824f  mov     [rbx+30h], rax
0x180008253  mov     [rbx+38h], rsi
0x180008257  mov     [rbx+48h], esi
0x18000825a  lea     rcx, [rbx+50h]; void *
0x18000825e  mov     [r11-18h], rcx
0x180008262  mov     [rcx+98h], rsi
0x180008269  mov     [rcx+0A0h], rsi
0x180008270  xor     edx, edx; Val
0x180008272  mov     r8d, 98h; Size
0x180008278  call    memset_0
0x18000827d  nop
0x18000827e  mov     dword ptr [rbx+0F8h], 1
0x180008288  xor     eax, eax
0x18000828a  mov     [rbx+100h], rax
0x180008291  mov     [rdi+110h], rbx
0x180008298  mov     [rdi+118h], rsi
0x18000829f  mov     [rdi+120h], rsi
0x1800082a6  mov     [rdi+128h], rdi
0x1800082ad  mov     [rdi+130h], rsi
0x1800082b4  mov     [rdi+138h], esi
0x1800082ba  lea     rax, [rdi+30h]
0x1800082be  mov     [rdi+140h], rax
0x1800082c5  mov     [rdi+148h], sil
0x1800082cc  mov     rax, rdi
0x1800082cf  mov     rbx, [rsp+38h+arg_8]
0x1800082d4  mov     rsi, [rsp+38h+arg_10]
0x1800082d9  add     rsp, 30h
0x1800082dd  pop     rdi
0x1800082de  retn
```
