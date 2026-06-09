# HttpGetExtendedInterface<IHttpContext,IHttpContext3>(IHttpServer *,IHttpContext *,IHttpContext3 * *)

- ea: `0x180005970`
- end: `0x1800059e3`
- name: `??$HttpGetExtendedInterface@VIHttpContext@@VIHttpContext3@@@@YAJPEAVIHttpServer@@PEAVIHttpContext@@PEAPEAVIHttpContext3@@@Z`
- size: `115`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800061e0`
- `0x180007e70`
- `0x180008080`

## callees

- `0x180005970`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall HttpGetExtendedInterface<IHttpContext,IHttpContext3>(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF

  v6 = 0;
  result = (*(__int64 (__fastcall **)(struct IHttpServer *, _QWORD, __int64 *))(*(_QWORD *)g_pGlobalInfo + 200LL))(
             g_pGlobalInfo,
             0,
             &v6);
  if ( (int)result >= 0 )
    return (*(__int64 (__fastcall **)(__int64, GUID *, __int64, GUID *, __int64))(*(_QWORD *)v6 + 224LL))(
             v6,
             &GUID_424c1b8c_a1ba_44d7_ac98_9f8f457701a5,
             a2,
             &GUID_bf53c022_ca4b_4349_a38e_a4b78ad897fb,
             a3);
  return result;
}

```

## disassembly

```asm
0x180005970  mov     r11, rsp
0x180005973  mov     [r11+10h], rbx
0x180005977  mov     [r11+8], rcx
0x18000597b  push    rdi
0x18000597c  sub     rsp, 30h
0x180005980  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180005987  mov     rbx, r8
0x18000598a  mov     rdi, rdx
0x18000598d  mov     qword ptr [r11+8], 0
0x180005995  lea     r8, [r11+8]
0x180005999  xor     edx, edx
0x18000599b  mov     rax, [rcx]
0x18000599e  mov     rax, [rax+0C8h]
0x1800059a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059aa  test    eax, eax
0x1800059ac  js      short loc_1800059D8
0x1800059ae  mov     rcx, [rsp+38h+arg_0]
0x1800059b3  lea     r9, _GUID_bf53c022_ca4b_4349_a38e_a4b78ad897fb
0x1800059ba  mov     r8, rdi
0x1800059bd  mov     [rsp+38h+var_18], rbx
0x1800059c2  lea     rdx, _GUID_424c1b8c_a1ba_44d7_ac98_9f8f457701a5
0x1800059c9  mov     rax, [rcx]
0x1800059cc  mov     rax, [rax+0E0h]
0x1800059d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059d8  mov     rbx, [rsp+38h+arg_8]
0x1800059dd  add     rsp, 30h
0x1800059e1  pop     rdi
0x1800059e2  retn
```
