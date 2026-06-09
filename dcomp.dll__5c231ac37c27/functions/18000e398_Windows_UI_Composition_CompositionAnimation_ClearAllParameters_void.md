# Windows::UI::Composition::CompositionAnimation::ClearAllParameters(void)

- ea: `0x18000e398`
- end: `0x18000e4a9`
- name: `?ClearAllParameters@CompositionAnimation@Composition@UI@Windows@@QEAAJXZ`
- size: `273`
- prototype: `__int64 __fastcall(Windows::UI::Composition::CompositionAnimation *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ae90`
- `0x1800bb810`

## callees

- `0x18000c924`
- `0x18000d8cc`
- `0x18000e398`
- `0x18000f334`
- `0x1800f6f10`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e430`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e430`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18000e49e`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18000e49e`
- `ntdll!RtlDeleteElementGenericTable` at `0x18000e419`
- `ntdll!RtlDeleteElementGenericTable` at `0x18000e419`
- `ntdll!RtlGetElementGenericTable` at `0x18000e440`
- `ntdll!RtlGetElementGenericTable` at `0x18000e440`
- `ntdll!RtlNumberGenericTableElements` at `0x18000e3c6`
- `ntdll!RtlNumberGenericTableElements` at `0x18000e3c6`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::CompositionAnimation::ClearAllParameters(
        Windows::UI::Composition::CompositionAnimation *this)
{
  struct _RTL_GENERIC_TABLE *v1; // rbp
  ULONG v3; // edi
  Microsoft::WRL2::ContextSession *v4; // rcx
  ParameterEntry *ElementGenericTable; // rax
  ParameterEntry *v6; // rbx
  struct IUnknown *v7; // rdx
  HSTRING v8; // r14
  __int64 Buffer; // [rsp+20h] [rbp-58h] BYREF
  int v11; // [rsp+28h] [rbp-50h]
  __int128 v12; // [rsp+30h] [rbp-48h]
  int v13; // [rsp+40h] [rbp-38h]

  v1 = (struct _RTL_GENERIC_TABLE *)((char *)this + 208);
  v3 = RtlNumberGenericTableElements((PRTL_GENERIC_TABLE)((char *)this + 208));
  while ( (--v3 & 0x80000000) == 0 )
  {
    ElementGenericTable = (ParameterEntry *)RtlGetElementGenericTable(v1, v3);
    v6 = ElementGenericTable;
    if ( ElementGenericTable )
    {
      v7 = (struct IUnknown *)*((_QWORD *)ElementGenericTable + 3);
      v8 = *(HSTRING *)ElementGenericTable;
      if ( v7 )
      {
        v4 = (Microsoft::WRL2::ContextSession *)*((_QWORD *)this + 3);
        *((_QWORD *)ElementGenericTable + 3) = 0;
        Microsoft::WRL2::ContextSession::EnqueueReleaseAndPassOwnershipWorker(v4, v7);
      }
      Buffer = *(_QWORD *)v6;
      v12 = 0;
      *((_DWORD *)v6 + 8) = 0;
      v11 = 0;
      v13 = 0;
      ParameterEntry::~ParameterEntry(v6);
      if ( !RtlDeleteElementGenericTable(v1, &Buffer) )
        RaiseFailFastException(0, 0, 1u);
      ParameterEntry::~ParameterEntry((ParameterEntry *)&Buffer);
      WindowsDeleteString(v8);
    }
  }
  *((_DWORD *)this + 80) = 0;
  Windows::UI::Composition::CompositionAnimation::InvalidateCache(this);
  return 0;
}

```

## disassembly

```asm
0x18000e398  mov     [rsp+arg_8], rbx
0x18000e39d  mov     [rsp+arg_10], rbp
0x18000e3a2  push    rsi
0x18000e3a3  push    rdi
0x18000e3a4  push    r14
0x18000e3a6  sub     rsp, 60h
0x18000e3aa  mov     rax, cs:__security_cookie
0x18000e3b1  xor     rax, rsp
0x18000e3b4  mov     [rsp+78h+var_20], rax
0x18000e3b9  lea     rbp, [rcx+0D0h]
0x18000e3c0  mov     rsi, rcx
0x18000e3c3  mov     rcx, rbp; Table
0x18000e3c6  call    cs:__imp_RtlNumberGenericTableElements
0x18000e3cc  mov     edi, eax
0x18000e3ce  jmp     short loc_18000E436
0x18000e3d0  mov     rcx, [rsi+18h]; this
0x18000e3d4  mov     qword ptr [rax+18h], 0
0x18000e3dc  call    ?EnqueueReleaseAndPassOwnershipWorker@ContextSession@WRL2@Microsoft@@AEAAXPEAUIUnknown@@@Z; Microsoft::WRL2::ContextSession::EnqueueReleaseAndPassOwnershipWorker(IUnknown *)
0x18000e3e1  mov     rax, [rbx]
0x18000e3e4  xorps   xmm0, xmm0
0x18000e3e7  mov     rcx, rbx; this
0x18000e3ea  mov     [rsp+78h+Buffer], rax
0x18000e3ef  movdqu  [rsp+78h+var_48], xmm0
0x18000e3f5  mov     dword ptr [rbx+20h], 0
0x18000e3fc  mov     [rsp+78h+var_50], 0
0x18000e404  mov     [rsp+78h+var_38], 0
0x18000e40c  call    ??1ParameterEntry@@QEAA@XZ; ParameterEntry::~ParameterEntry(void)
0x18000e411  lea     rdx, [rsp+78h+Buffer]; Buffer
0x18000e416  mov     rcx, rbp; Table
0x18000e419  call    cs:__imp_RtlDeleteElementGenericTable
0x18000e41f  test    al, al
0x18000e421  jz      short loc_18000E496
0x18000e423  lea     rcx, [rsp+78h+Buffer]; this
0x18000e428  call    ??1ParameterEntry@@QEAA@XZ; ParameterEntry::~ParameterEntry(void)
0x18000e42d  mov     rcx, r14; string
0x18000e430  call    cs:__imp_WindowsDeleteString
0x18000e436  sub     edi, 1
0x18000e439  js      short loc_18000E460
0x18000e43b  mov     edx, edi; I
0x18000e43d  mov     rcx, rbp; Table
0x18000e440  call    cs:__imp_RtlGetElementGenericTable
0x18000e446  mov     rbx, rax
0x18000e449  test    rax, rax
0x18000e44c  jz      short loc_18000E436
0x18000e44e  mov     rdx, [rax+18h]; struct IUnknown *
0x18000e452  mov     r14, [rax]
0x18000e455  test    rdx, rdx
0x18000e458  jnz     loc_18000E3D0
0x18000e45e  jmp     short loc_18000E3E1
0x18000e460  mov     rcx, rsi; this
0x18000e463  mov     dword ptr [rsi+140h], 0
0x18000e46d  call    ?InvalidateCache@CompositionAnimation@Composition@UI@Windows@@IEAAXXZ; Windows::UI::Composition::CompositionAnimation::InvalidateCache(void)
0x18000e472  xor     eax, eax
0x18000e474  mov     rcx, [rsp+78h+var_20]
0x18000e479  xor     rcx, rsp; StackCookie
0x18000e47c  call    __security_check_cookie
0x18000e481  lea     r11, [rsp+78h+var_18]
0x18000e486  mov     rbx, [r11+28h]
0x18000e48a  mov     rbp, [r11+30h]
0x18000e48e  mov     rsp, r11
0x18000e491  pop     r14
0x18000e493  pop     rdi
0x18000e494  pop     rsi
0x18000e495  retn
0x18000e496  xor     edx, edx; pContextRecord
0x18000e498  xor     ecx, ecx; pExceptionRecord
0x18000e49a  lea     r8d, [rdx+1]; dwFlags
0x18000e49e  call    cs:__imp_RaiseFailFastException
0x18000e4a4  jmp     loc_18000E423
```
