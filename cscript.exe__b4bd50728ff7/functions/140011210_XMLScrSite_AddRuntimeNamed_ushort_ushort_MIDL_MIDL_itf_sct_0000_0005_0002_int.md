# XMLScrSite::AddRuntimeNamed(ushort *,ushort *,__MIDL___MIDL_itf_sct_0000_0005_0002,int)

- ea: `0x140011210`
- end: `0x1400112d9`
- name: `?AddRuntimeNamed@XMLScrSite@@UEAAJPEAG0W4__MIDL___MIDL_itf_sct_0000_0005_0002@@H@Z`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140011210`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall XMLScrSite::AddRuntimeNamed(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, int a5)
{
  __int64 v5; // rax
  int v9; // ebx
  _QWORD v11[7]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v12; // [rsp+70h] [rbp+8h] BYREF

  v5 = *(_QWORD *)(a1 + 16);
  v12 = 0;
  v11[0] = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(v5 + 624) + 128LL))(*(_QWORD *)(v5 + 624), &v12);
  if ( v9 >= 0 )
  {
    v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v12)(v12, &IID_IWshRuntime, v11);
    if ( v9 >= 0 )
      v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, int))(*(_QWORD *)v11[0] + 24LL))(
             v11[0],
             a2,
             a3,
             a4,
             a5);
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v11[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v11[0] + 16LL))(v11[0]);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140011210  push    rbx
0x140011212  push    rbp
0x140011213  push    rsi
0x140011214  push    rdi
0x140011215  sub     rsp, 48h
0x140011219  mov     rax, [rcx+10h]
0x14001121d  mov     rbp, rdx
0x140011220  mov     [rsp+68h+arg_0], 0
0x140011229  lea     rdx, [rsp+68h+arg_0]
0x14001122e  mov     [rsp+68h+var_38], 0
0x140011237  mov     edi, r9d
0x14001123a  mov     rsi, r8
0x14001123d  mov     rcx, [rax+270h]
0x140011244  mov     rax, [rcx]
0x140011247  mov     rax, [rax+80h]
0x14001124e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011253  mov     ebx, eax
0x140011255  test    eax, eax
0x140011257  js      short loc_1400112A2
0x140011259  mov     rcx, [rsp+68h+arg_0]
0x14001125e  lea     r8, [rsp+68h+var_38]
0x140011263  lea     rdx, ?IID_IWshRuntime@@3U_GUID@@B; _GUID const IID_IWshRuntime
0x14001126a  mov     rax, [rcx]
0x14001126d  mov     rax, [rax]
0x140011270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011275  mov     ebx, eax
0x140011277  test    eax, eax
0x140011279  js      short loc_1400112A2
0x14001127b  mov     rcx, [rsp+68h+var_38]
0x140011280  mov     r9d, edi
0x140011283  mov     edx, [rsp+68h+arg_20]
0x14001128a  mov     r8, rsi
0x14001128d  mov     [rsp+68h+var_48], edx
0x140011291  mov     rdx, rbp
0x140011294  mov     rax, [rcx]
0x140011297  mov     rax, [rax+18h]
0x14001129b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400112a0  mov     ebx, eax
0x1400112a2  mov     rcx, [rsp+68h+arg_0]
0x1400112a7  test    rcx, rcx
0x1400112aa  jz      short loc_1400112B8
0x1400112ac  mov     rax, [rcx]
0x1400112af  mov     rax, [rax+10h]
0x1400112b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400112b8  mov     rcx, [rsp+68h+var_38]
0x1400112bd  test    rcx, rcx
0x1400112c0  jz      short loc_1400112CE
0x1400112c2  mov     rax, [rcx]
0x1400112c5  mov     rax, [rax+10h]
0x1400112c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400112ce  mov     eax, ebx
0x1400112d0  add     rsp, 48h
0x1400112d4  pop     rdi
0x1400112d5  pop     rsi
0x1400112d6  pop     rbp
0x1400112d7  pop     rbx
0x1400112d8  retn
```
