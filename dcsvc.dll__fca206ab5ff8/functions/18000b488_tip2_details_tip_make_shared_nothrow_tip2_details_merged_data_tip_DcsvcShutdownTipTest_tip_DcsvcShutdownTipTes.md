# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>,>(void)

- ea: `0x18000b488`
- end: `0x18000b5ba`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `306`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c854`

## callees

- `0x18000a12c`
- `0x18000b488`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000b56b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000b56b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b49f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b49f`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>,>(
        _QWORD *a1)
{
  wil::details::in1diag3 *v2; // rcx
  char *v3; // rbx
  _QWORD *result; // rax

  v3 = (char *)CoTaskMemAlloc(0x128u);
  if ( !v3 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v2);
  *(_QWORD *)v3 = &tip2::details::test_data_interface::`vftable';
  *((_QWORD *)v3 + 2) = 0;
  *((_QWORD *)v3 + 1) = v3;
  *((_QWORD *)v3 + 10) = 0;
  *((_QWORD *)v3 + 11) = 0;
  *((_QWORD *)v3 + 12) = 0;
  *((_QWORD *)v3 + 13) = 0;
  *((_QWORD *)v3 + 14) = 0;
  *((_QWORD *)v3 + 15) = 0;
  *((_QWORD *)v3 + 16) = 0;
  *((_QWORD *)v3 + 17) = 0;
  *((_QWORD *)v3 + 18) = 0;
  *((_DWORD *)v3 + 18) = 0;
  *(_OWORD *)(v3 + 152) = 0;
  v3[168] = 0;
  *((_WORD *)v3 + 85) = -1;
  *((_QWORD *)v3 + 22) = 0;
  *((_QWORD *)v3 + 23) = 0;
  *((_QWORD *)v3 + 31) = 0;
  *((_QWORD *)v3 + 4) = "DcsvcShutdownTipTest";
  *(_DWORD *)(v3 + 42) = 0;
  *((_DWORD *)v3 + 48) = 0;
  *((_DWORD *)v3 + 60) = 0;
  *((_DWORD *)v3 + 6) = 60524637;
  *((_DWORD *)v3 + 7) = 53760;
  *((_WORD *)v3 + 20) = 769;
  *((_WORD *)v3 + 23) = 0;
  *((_QWORD *)v3 + 6) = 0;
  *((_QWORD *)v3 + 7) = 0;
  *((_QWORD *)v3 + 8) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)v3 + 5);
  *((_QWORD *)v3 + 34) = 0;
  *(_QWORD *)v3 = &tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>::`vftable';
  *((_QWORD *)v3 + 33) = v3 + 16;
  result = a1;
  v3[280] = 0;
  *((_DWORD *)v3 + 72) = 1;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x18000b488  mov     [rsp+arg_0], rbx
0x18000b48d  mov     [rsp+arg_8], rsi
0x18000b492  push    rdi
0x18000b493  sub     rsp, 20h
0x18000b497  mov     rdi, rcx
0x18000b49a  mov     ecx, 128h; cb
0x18000b49f  call    cs:__imp_CoTaskMemAlloc
0x18000b4a5  xor     esi, esi
0x18000b4a7  mov     rbx, rax
0x18000b4aa  test    rax, rax
0x18000b4ad  jz      loc_18000B5B4
0x18000b4b3  xor     edx, edx
0x18000b4b5  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x18000b4bc  mov     [rbx], rax
0x18000b4bf  lea     rcx, aDcsvcshutdownt; "DcsvcShutdownTipTest"
0x18000b4c6  mov     [rbx+10h], rsi
0x18000b4ca  xorps   xmm0, xmm0
0x18000b4cd  mov     [rbx+8], rbx
0x18000b4d1  mov     [rbx+50h], rsi
0x18000b4d5  mov     [rbx+58h], rsi
0x18000b4d9  mov     [rbx+60h], rsi
0x18000b4dd  mov     [rbx+68h], rsi
0x18000b4e1  mov     [rbx+70h], rsi
0x18000b4e5  mov     [rbx+78h], rsi
0x18000b4e9  mov     [rbx+80h], rsi
0x18000b4f0  mov     [rbx+88h], rsi
0x18000b4f7  mov     [rbx+90h], rsi
0x18000b4fe  mov     [rbx+48h], esi
0x18000b501  movups  xmmword ptr [rbx+98h], xmm0
0x18000b508  mov     [rbx+0A8h], sil
0x18000b50f  mov     word ptr [rbx+0AAh], 0FFFFh
0x18000b518  mov     [rbx+0B0h], rsi
0x18000b51f  mov     [rbx+0B8h], rsi
0x18000b526  mov     [rbx+0F8h], rsi
0x18000b52d  mov     [rbx+20h], rcx
0x18000b531  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000b538  mov     [rbx+2Ah], edx
0x18000b53b  mov     [rbx+0C0h], esi
0x18000b541  mov     [rbx+0F0h], esi
0x18000b547  mov     dword ptr [rbx+18h], 39B885Dh
0x18000b54e  mov     dword ptr [rbx+1Ch], 0D200h
0x18000b555  mov     word ptr [rbx+28h], 301h
0x18000b55b  mov     [rbx+2Eh], dx
0x18000b55f  mov     [rbx+30h], rsi
0x18000b563  mov     [rbx+38h], rsi
0x18000b567  mov     [rbx+40h], rsi
0x18000b56b  call    cs:__imp_InitializeCriticalSection
0x18000b571  mov     [rbx+110h], rsi
0x18000b578  lea     rax, ??_7?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>::`vftable'
0x18000b57f  mov     [rbx], rax
0x18000b582  lea     rax, [rbx+10h]
0x18000b586  mov     [rbx+108h], rax
0x18000b58d  mov     rax, rdi
0x18000b590  mov     [rbx+118h], sil
0x18000b597  mov     rsi, [rsp+28h+arg_8]
0x18000b59c  mov     dword ptr [rbx+120h], 1
0x18000b5a6  mov     [rdi], rbx
0x18000b5a9  mov     rbx, [rsp+28h+arg_0]
0x18000b5ae  add     rsp, 20h
0x18000b5b2  pop     rdi
0x18000b5b3  retn
0x18000b5b4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
