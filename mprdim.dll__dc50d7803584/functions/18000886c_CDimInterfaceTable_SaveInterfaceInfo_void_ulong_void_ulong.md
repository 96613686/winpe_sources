# CDimInterfaceTable::SaveInterfaceInfo(void *,ulong,void *,ulong)

- ea: `0x18000886c`
- end: `0x180008967`
- name: `?SaveInterfaceInfo@CDimInterfaceTable@@QEAAKPEAXK0K@Z`
- size: `251`
- prototype: `unsigned int(CDimInterfaceTable *__hidden this, void *, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800174d0`

## callees

- `0x180005550`
- `0x1800055f0`
- `0x180005670`
- `0x180006ce0`
- `0x18000886c`
- `0x180026e0c`
- `0x180048010`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000892d`
- `ADVAPI32!RegSetValueExW` at `0x18000892d`
- `ADVAPI32!RegCloseKey` at `0x18000893d`
- `ADVAPI32!RegCloseKey` at `0x18000893d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDimInterfaceTable::SaveInterfaceInfo(
        CDimInterfaceTable *this,
        unsigned __int64 a2,
        int a3,
        const BYTE *a4,
        DWORD cbData)
{
  CDimInterfaceTable *v8; // rdi
  unsigned int v9; // ebx
  wchar_t *v10; // rax
  struct _GUID *v12; // [rsp+30h] [rbp-48h] BYREF
  std::tr1::_Ref_count_base *v13; // [rsp+38h] [rbp-40h]
  struct _GUID v14; // [rsp+40h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+8h] BYREF

  hKey = (HKEY)this;
  v8 = g_pCDimInterfaceTable;
  CDimInterfaceTable::AcquireShared(g_pCDimInterfaceTable);
  hKey = 0;
  CDimInterfaceTable::GetCDimInterface((__int64)v8, &v12, a2);
  if ( v12 )
  {
    v10 = (wchar_t *)(*(__int64 (__fastcall **)(struct _GUID *))(*(_QWORD *)&v12->Data1 + 280LL))(v12);
    v14 = v12[194];
    v9 = CDimInterfaceTable::RegOpenInterfaceTransportKey(v8, &v14, v10, a3, &hKey);
    if ( !v9 )
    {
      v9 = RegSetValueExW(hKey, L"InterfaceInfo", 0, 3u, a4, cbData);
      RegCloseKey(hKey);
    }
  }
  else
  {
    v9 = 6;
  }
  if ( v13 )
    std::tr1::_Ref_count_base::_Decref(v13);
  CDimInterfaceTable::ReleaseShared(v8);
  return v9;
}

```

## disassembly

```asm
0x18000886c  mov     [rsp+hKey], rcx
0x180008871  push    rbx
0x180008872  push    rbp
0x180008873  push    rsi
0x180008874  push    rdi
0x180008875  sub     rsp, 58h
0x180008879  mov     rsi, r9
0x18000887c  mov     ebp, r8d
0x18000887f  mov     rbx, rdx
0x180008882  mov     rdi, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; CDimInterfaceTable * g_pCDimInterfaceTable
0x180008889  mov     rcx, rdi; this
0x18000888c  call    ?AcquireShared@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::AcquireShared(void)
0x180008891  mov     [rsp+78h+hKey], 0
0x18000889d  mov     r8, rbx
0x1800088a0  lea     rdx, [rsp+78h+var_48]
0x1800088a5  mov     rcx, rdi
0x1800088a8  call    ?GetCDimInterface@CDimInterfaceTable@@QEAA?AV?$shared_ptr@VCDimInterface@@@tr1@std@@QEAX@Z; CDimInterfaceTable::GetCDimInterface(void * const)
0x1800088ad  nop
0x1800088ae  mov     rcx, [rsp+78h+var_48]
0x1800088b3  test    rcx, rcx
0x1800088b6  jnz     short loc_1800088C0
0x1800088b8  lea     ebx, [rcx+6]
0x1800088bb  jmp     loc_180008944
0x1800088c0  mov     rax, [rcx]
0x1800088c3  mov     rax, [rax+118h]
0x1800088ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088cf  mov     r8, rax; String1
0x1800088d2  mov     rax, [rsp+78h+var_48]
0x1800088d7  movups  xmm0, xmmword ptr [rax+0C20h]
0x1800088de  movdqu  xmmword ptr [rsp+78h+var_38.Data1], xmm0
0x1800088e4  lea     rax, [rsp+78h+hKey]
0x1800088ec  mov     [rsp+78h+lpData], rax; HKEY *
0x1800088f1  mov     r9d, ebp; unsigned int
0x1800088f4  lea     rdx, [rsp+78h+var_38]; struct _GUID *
0x1800088f9  mov     rcx, rdi; this
0x1800088fc  call    ?RegOpenInterfaceTransportKey@CDimInterfaceTable@@AEAAKU_GUID@@PEAGKAEAPEAUHKEY__@@@Z; CDimInterfaceTable::RegOpenInterfaceTransportKey(_GUID,ushort *,ulong,HKEY__ * &)
0x180008901  mov     ebx, eax
0x180008903  test    eax, eax
0x180008905  jnz     short loc_180008944
0x180008907  mov     eax, [rsp+78h+arg_20]
0x18000890e  mov     [rsp+78h+cbData], eax; cbData
0x180008912  mov     [rsp+78h+lpData], rsi; lpData
0x180008917  lea     r9d, [rbx+3]; dwType
0x18000891b  xor     r8d, r8d; Reserved
0x18000891e  lea     rdx, aInterfaceinfo; "InterfaceInfo"
0x180008925  mov     rcx, [rsp+78h+hKey]; hKey
0x18000892d  call    cs:__imp_RegSetValueExW
0x180008933  mov     ebx, eax
0x180008935  mov     rcx, [rsp+78h+hKey]; hKey
0x18000893d  call    cs:__imp_RegCloseKey
0x180008943  nop
0x180008944  mov     rcx, [rsp+78h+var_40]; this
0x180008949  test    rcx, rcx
0x18000894c  jz      short loc_180008954
0x18000894e  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x180008953  nop
0x180008954  mov     rcx, rdi; this
0x180008957  call    ?ReleaseShared@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::ReleaseShared(void)
0x18000895c  mov     eax, ebx
0x18000895e  add     rsp, 58h
0x180008962  pop     rdi
0x180008963  pop     rsi
0x180008964  pop     rbp
0x180008965  pop     rbx
0x180008966  retn
```
