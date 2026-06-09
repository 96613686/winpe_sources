# DataSharingServiceTelemetry::RemoveExpiredTokens::RemoveExpiredTokens(wistd::integral_constant<char,0>)

- ea: `0x18000c558`
- end: `0x18000c621`
- name: `??$?0$$V@RemoveExpiredTokens@DataSharingServiceTelemetry@@AEAA@U?$integral_constant@D$0A@@wistd@@@Z`
- size: `201`
- prototype: `DataSharingServiceTelemetry::RemoveExpiredTokens *__fastcall(DataSharingServiceTelemetry::RemoveExpiredTokens *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000d68c`

## callees

- `0x18000e91c`
- `0x18001b30a`

## string_xrefs

- `0x18000c56f`: `RemoveExpiredTokens`

## pseudocode

```c
DataSharingServiceTelemetry::RemoveExpiredTokens *__fastcall DataSharingServiceTelemetry::RemoveExpiredTokens::RemoveExpiredTokens(
        DataSharingServiceTelemetry::RemoveExpiredTokens *this)
{
  char *v1; // rbx
  _QWORD *v3; // rcx

  v1 = (char *)this + 8;
  *((_DWORD *)this + 2) = 0;
  *((_BYTE *)this + 12) = 0;
  *((_BYTE *)this + 72) = 0;
  v3 = (_QWORD *)((char *)this + 88);
  *((_DWORD *)v1 + 10) = 0;
  *((_QWORD *)v1 + 6) = "RemoveExpiredTokens";
  *((_QWORD *)v1 + 7) = 0;
  *((_DWORD *)v1 + 18) = 0;
  v3[19] = 0;
  v3[20] = 0;
  memset_0(v3, 0, 0x98u);
  *((_DWORD *)v1 + 62) = 1;
  *((_QWORD *)v1 + 32) = 0;
  *((_QWORD *)this + 34) = v1;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 40) = (char *)this + 48;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = this;
  *((_QWORD *)this + 38) = 0;
  *((_DWORD *)this + 78) = 0;
  *((_BYTE *)this + 328) = 0;
  *(_QWORD *)this = &DataSharingServiceTelemetry::RemoveExpiredTokens::`vftable';
  DataSharingServiceTelemetry::RemoveExpiredTokens::StartActivity(this);
  return this;
}

```

## disassembly

```asm
0x18000c558  mov     [rsp+arg_0], rbx
0x18000c55d  mov     [rsp+arg_8], rsi
0x18000c562  push    rdi
0x18000c563  sub     rsp, 20h
0x18000c567  lea     rbx, [rcx+8]
0x18000c56b  xor     esi, esi
0x18000c56d  mov     [rbx], esi
0x18000c56f  lea     rax, aRemoveexpiredt; "RemoveExpiredTokens"
0x18000c576  mov     [rbx+4], sil
0x18000c57a  mov     rdi, rcx
0x18000c57d  mov     [rbx+40h], sil
0x18000c581  lea     rcx, [rbx+50h]; void *
0x18000c585  mov     [rbx+28h], esi
0x18000c588  xor     edx, edx; Val
0x18000c58a  mov     [rbx+30h], rax
0x18000c58e  mov     r8d, 98h; Size
0x18000c594  mov     [rbx+38h], rsi
0x18000c598  mov     [rbx+48h], esi
0x18000c59b  mov     [rcx+98h], rsi
0x18000c5a2  mov     [rcx+0A0h], rsi
0x18000c5a9  call    memset_0
0x18000c5ae  mov     dword ptr [rbx+0F8h], 1
0x18000c5b8  xor     eax, eax
0x18000c5ba  mov     [rbx+100h], rax
0x18000c5c1  mov     rcx, rdi; this
0x18000c5c4  mov     [rdi+110h], rbx
0x18000c5cb  lea     rax, [rdi+30h]
0x18000c5cf  mov     [rdi+118h], rsi
0x18000c5d6  mov     [rdi+140h], rax
0x18000c5dd  lea     rax, ??_7RemoveExpiredTokens@DataSharingServiceTelemetry@@6B@; const DataSharingServiceTelemetry::RemoveExpiredTokens::`vftable'
0x18000c5e4  mov     [rdi+120h], rsi
0x18000c5eb  mov     [rdi+128h], rdi
0x18000c5f2  mov     [rdi+130h], rsi
0x18000c5f9  mov     [rdi+138h], esi
0x18000c5ff  mov     [rdi+148h], sil
0x18000c606  mov     [rdi], rax
0x18000c609  call    ?StartActivity@RemoveExpiredTokens@DataSharingServiceTelemetry@@QEAAXXZ; DataSharingServiceTelemetry::RemoveExpiredTokens::StartActivity(void)
0x18000c60e  mov     rbx, [rsp+28h+arg_0]
0x18000c613  mov     rax, rdi
0x18000c616  mov     rsi, [rsp+28h+arg_8]
0x18000c61b  add     rsp, 20h
0x18000c61f  pop     rdi
0x18000c620  retn
```
