# GetDataConvert(IDataConvert * *)

- ea: `0x180020fbc`
- end: `0x18002109e`
- name: `?GetDataConvert@@YAJPEAPEAUIDataConvert@@@Z`
- size: `226`
- prototype: `__int64 __fastcall(struct IDataConvert **)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c400`
- `0x1800210a4`
- `0x1800257ec`

## callees

- `0x180020fbc`
- `0x18002145c`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180020fea`
- `KERNEL32!GetCurrentThreadId` at `0x180020fea`
- `KERNEL32!LeaveCriticalSection` at `0x18002107f`
- `KERNEL32!LeaveCriticalSection` at `0x18002107f`
- `ole32!CoCreateInstance` at `0x180021034`
- `ole32!CoCreateInstance` at `0x180021034`
- `MSDART!UMSEnterCSWraper` at `0x180020fd8`
- `MSDART!UMSEnterCSWraper` at `0x180020fd8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetDataConvert(struct IDataConvert **a1)
{
  _DWORD *v2; // rbx
  HRESULT Instance; // edi
  __int64 v5; // rcx

  v2 = g_pcsDataConvert;
  UMSEnterCSWraper(g_pcsDataConvert);
  if ( !v2[3] )
    v2[2] = GetCurrentThreadId();
  ++v2[3];
  ++v2[4];
  if ( g_pIDataConvert )
  {
    Instance = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)g_pIDataConvert + 8LL))(g_pIDataConvert);
  }
  else
  {
    Instance = CoCreateInstance(&CLSID_OLEDB_CONVERSIONLIBRARY, 0, 1u, &IID_IDataConvert, &g_pIDataConvert);
    if ( Instance >= 0 )
      Instance = SetVersionDC();
  }
  *a1 = (struct IDataConvert *)g_pIDataConvert;
  --v2[4];
  if ( v2[3]-- == 1 )
    v2[2] = -1;
  v5 = *(_QWORD *)v2;
  --*(_DWORD *)(v5 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180020fbc  mov     [rsp+arg_8], rbx
0x180020fc1  mov     [rsp+arg_10], rsi
0x180020fc6  push    rdi
0x180020fc7  sub     rsp, 30h
0x180020fcb  mov     rsi, rcx
0x180020fce  mov     rbx, cs:?g_pcsDataConvert@@3PEAVCFoxCriticalSection@@EA; CFoxCriticalSection * g_pcsDataConvert
0x180020fd5  mov     rcx, rbx
0x180020fd8  call    cs:__imp_UMSEnterCSWraper
0x180020fdf  nop     dword ptr [rax+rax+00h]
0x180020fe4  cmp     dword ptr [rbx+0Ch], 0
0x180020fe8  jnz     short loc_180020FF9
0x180020fea  call    cs:__imp_GetCurrentThreadId
0x180020ff1  nop     dword ptr [rax+rax+00h]
0x180020ff6  mov     [rbx+8], eax
0x180020ff9  mov     r8d, 1; dwClsContext
0x180020fff  add     [rbx+0Ch], r8d
0x180021003  add     [rbx+10h], r8d
0x180021007  mov     [rsp+38h+arg_0], rbx
0x18002100c  mov     rcx, cs:?g_pIDataConvert@@3PEAUIDataConvert@@EA; IDataConvert * g_pIDataConvert
0x180021013  test    rcx, rcx
0x180021016  jnz     short loc_18002104F
0x180021018  lea     rax, ?g_pIDataConvert@@3PEAUIDataConvert@@EA; IDataConvert * g_pIDataConvert
0x18002101f  mov     [rsp+38h+ppv], rax; ppv
0x180021024  lea     r9, IID_IDataConvert; riid
0x18002102b  xor     edx, edx; pUnkOuter
0x18002102d  lea     rcx, CLSID_OLEDB_CONVERSIONLIBRARY; rclsid
0x180021034  call    cs:__imp_CoCreateInstance
0x18002103b  nop     dword ptr [rax+rax+00h]
0x180021040  mov     edi, eax
0x180021042  test    eax, eax
0x180021044  js      short loc_18002105D
0x180021046  call    SetVersionDC
0x18002104b  mov     edi, eax
0x18002104d  jmp     short loc_18002105D
0x18002104f  xor     edi, edi
0x180021051  mov     rax, [rcx]
0x180021054  mov     rax, [rax+8]
0x180021058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002105d  mov     rax, cs:?g_pIDataConvert@@3PEAUIDataConvert@@EA; IDataConvert * g_pIDataConvert
0x180021064  mov     [rsi], rax
0x180021067  or      ecx, 0FFFFFFFFh
0x18002106a  add     [rbx+10h], ecx
0x18002106d  add     [rbx+0Ch], ecx
0x180021070  jnz     short loc_180021075
0x180021072  mov     [rbx+8], ecx
0x180021075  mov     rcx, [rbx]
0x180021078  dec     dword ptr [rcx+30h]
0x18002107b  add     rcx, 8; lpCriticalSection
0x18002107f  call    cs:__imp_LeaveCriticalSection
0x180021086  nop     dword ptr [rax+rax+00h]
0x18002108b  mov     eax, edi
0x18002108d  mov     rbx, [rsp+38h+arg_8]
0x180021092  mov     rsi, [rsp+38h+arg_10]
0x180021097  add     rsp, 30h
0x18002109b  pop     rdi
0x18002109c  retn
```
