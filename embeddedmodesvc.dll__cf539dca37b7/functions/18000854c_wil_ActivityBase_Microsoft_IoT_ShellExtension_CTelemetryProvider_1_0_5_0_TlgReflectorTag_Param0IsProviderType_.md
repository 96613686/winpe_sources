# wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)

- ea: `0x18000854c`
- end: `0x180008606`
- name: `??0?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z`
- size: `186`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009690`
- `0x18000af90`
- `0x18000f710`
- `0x18000f748`
- `0x180011290`
- `0x180012790`
- `0x1800129c0`
- `0x180012c00`

## callees

- `0x1800035a0`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  _QWORD *v4; // rcx

  *(_QWORD *)a1 = &wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable';
  v3 = a1 + 8;
  *(_DWORD *)(a1 + 8) = 0;
  *(_BYTE *)(a1 + 12) = 0;
  *(_BYTE *)(a1 + 72) = 0;
  *(_DWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = a2;
  *(_QWORD *)(a1 + 64) = 0;
  *(_DWORD *)(a1 + 80) = 0;
  v4 = (_QWORD *)(a1 + 88);
  v4[19] = 0;
  v4[20] = 0;
  memset_0(v4, 0, 0x98u);
  *(_DWORD *)(v3 + 248) = 1;
  *(_QWORD *)(v3 + 256) = 0;
  *(_QWORD *)(a1 + 272) = v3;
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
0x18000854c  mov     [rsp+arg_0], rbx
0x180008551  mov     [rsp+arg_8], rsi
0x180008556  push    rdi
0x180008557  sub     rsp, 20h
0x18000855b  mov     rdi, rcx
0x18000855e  lea     rax, ??_7?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x180008565  mov     [rcx], rax
0x180008568  lea     rbx, [rcx+8]
0x18000856c  xor     esi, esi
0x18000856e  mov     [rbx], esi
0x180008570  mov     [rbx+4], sil
0x180008574  mov     [rbx+40h], sil
0x180008578  mov     [rbx+28h], esi
0x18000857b  mov     [rbx+30h], rdx
0x18000857f  mov     [rbx+38h], rsi
0x180008583  mov     [rbx+48h], esi
0x180008586  lea     rcx, [rbx+50h]; void *
0x18000858a  mov     [rcx+98h], rsi
0x180008591  mov     [rcx+0A0h], rsi
0x180008598  xor     edx, edx; Val
0x18000859a  mov     r8d, 98h; Size
0x1800085a0  call    memset_0
0x1800085a5  mov     dword ptr [rbx+0F8h], 1
0x1800085af  xor     eax, eax
0x1800085b1  mov     [rbx+100h], rax
0x1800085b8  mov     [rdi+110h], rbx
0x1800085bf  mov     [rdi+118h], rsi
0x1800085c6  mov     [rdi+120h], rsi
0x1800085cd  mov     [rdi+128h], rdi
0x1800085d4  mov     [rdi+130h], rsi
0x1800085db  mov     [rdi+138h], esi
0x1800085e1  lea     rax, [rdi+30h]
0x1800085e5  mov     [rdi+140h], rax
0x1800085ec  mov     [rdi+148h], sil
0x1800085f3  mov     rax, rdi
0x1800085f6  mov     rbx, [rsp+28h+arg_0]
0x1800085fb  mov     rsi, [rsp+28h+arg_8]
0x180008600  add     rsp, 20h
0x180008604  pop     rdi
0x180008605  retn
```
