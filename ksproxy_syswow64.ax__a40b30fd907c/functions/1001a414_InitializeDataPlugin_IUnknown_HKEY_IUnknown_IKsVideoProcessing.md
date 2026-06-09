# InitializeDataPlugin(IUnknown *,HKEY__ *,IUnknown * *,IKsVideoProcessing * *)

- ea: `0x1001a414`
- end: `0x1001a510`
- name: `?InitializeDataPlugin@@YGJPAUIUnknown@@PAUHKEY__@@PAPAU1@PAPAUIKsVideoProcessing@@@Z`
- size: `252`
- prototype: `LSTATUS __userpurge@<eax>(HKEY@<edx>, IUnknown *@<ecx>, struct IUnknown *ppv, HKEY, struct IUnknown **, struct IKsVideoProcessing **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1001a516`

## callees

- `0x10019fd3`
- `0x1001a2cc`
- `0x1001a414`
- `0x1002d510`
- `0x1003aba0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1001a465`
- `KERNEL32!QueryPerformanceCounter` at `0x1001a4c7`
- `KERNEL32!QueryPerformanceCounter` at `0x1001a465`
- `KERNEL32!QueryPerformanceCounter` at `0x1001a4c7`
- `ole32!CoCreateInstance` at `0x1001a47d`
- `ole32!CoCreateInstance` at `0x1001a47d`

## pseudocode

```c
LSTATUS __userpurge InitializeDataPlugin@<eax>(
        HKEY a1@<edx>,
        IUnknown *a2@<ecx>,
        struct IUnknown *ppv,
        HKEY a4,
        struct IUnknown **a5,
        struct IKsVideoProcessing **a6)
{
  LSTATUS PlginCLSID; // edi
  LARGE_INTEGER PerformanceCount; // [esp+10h] [ebp-28h] BYREF
  LARGE_INTEGER v10; // [esp+18h] [ebp-20h] BYREF
  IID rclsid; // [esp+24h] [ebp-14h] BYREF

  PerformanceCount.QuadPart = 0;
  v10.QuadPart = 0;
  PlginCLSID = GetPlginCLSID(a1, (BYTE *)&rclsid);
  if ( PlginCLSID >= 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      QueryPerformanceCounter(&PerformanceCount);
    PlginCLSID = CoCreateInstance(
                   &rclsid,
                   a2,
                   0x401u,
                   &_GUID_00000000_0000_0000_c000_000000000046,
                   (LPVOID *)&ppv->__vftable);
    if ( PlginCLSID >= 0 )
    {
      PlginCLSID = (*(int (__thiscall **)(_DWORD, IUnknown_vtbl *, GUID *, HKEY))ppv->QueryInterface)(
                     *(_DWORD *)ppv->QueryInterface,
                     ppv->__vftable,
                     &_GUID_2efc7721_05da_4ac6_8300_635e373d839e,
                     a4);
      if ( PlginCLSID >= 0 )
      {
        (*(void (__thiscall **)(_DWORD, _DWORD))(**(_DWORD **)a4 + 8))(*(_DWORD *)(**(_DWORD **)a4 + 8), *(_DWORD *)a4);
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        {
          QueryPerformanceCounter(&v10);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_i(
              0xAu,
              (int)WPP_GLOBAL_Control,
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              LOBYTE(v10.LowPart) - LOBYTE(PerformanceCount.LowPart),
              (unsigned __int64)(v10.QuadPart - PerformanceCount.QuadPart) >> 32);
        }
      }
    }
  }
  return PlginCLSID;
}

```

## disassembly

```asm
0x1001a414  mov     edi, edi
0x1001a416  push    ebp
0x1001a417  mov     ebp, esp
0x1001a419  sub     esp, 2Ch
0x1001a41c  mov     eax, ___security_cookie
0x1001a421  xor     eax, ebp
0x1001a423  mov     [ebp+var_4], eax
0x1001a426  push    ebx
0x1001a427  mov     ebx, [ebp+arg_4]
0x1001a42a  mov     eax, edx
0x1001a42c  mov     [ebp+pUnkOuter], ecx
0x1001a42f  lea     edx, [ebp+rclsid]
0x1001a432  xor     ecx, ecx
0x1001a434  push    esi; struct _GUID *
0x1001a435  mov     esi, [ebp+ppv]
0x1001a438  mov     dword ptr [ebp+PerformanceCount], ecx
0x1001a43b  mov     dword ptr [ebp+PerformanceCount+4], ecx
0x1001a43e  mov     dword ptr [ebp+var_20], ecx
0x1001a441  mov     dword ptr [ebp+var_20+4], ecx
0x1001a444  mov     ecx, eax
0x1001a446  push    edi; HKEY
0x1001a447  call    ?GetPlginCLSID@@YGJPAUHKEY__@@PAU_GUID@@@Z; GetPlginCLSID(HKEY__ *,_GUID *)
0x1001a44c  mov     edi, eax
0x1001a44e  test    edi, edi
0x1001a450  js      loc_1001A4FD
0x1001a456  mov     eax, _WPP_GLOBAL_Control
0x1001a45b  test    byte ptr [eax+1Ch], 20h
0x1001a45f  jz      short loc_1001A46B
0x1001a461  lea     eax, [ebp+PerformanceCount]
0x1001a464  push    eax; lpPerformanceCount
0x1001a465  call    ds:__imp__QueryPerformanceCounter@4; QueryPerformanceCounter(x)
0x1001a46b  push    esi; ppv
0x1001a46c  push    offset __GUID_00000000_0000_0000_c000_000000000046; riid
0x1001a471  push    401h; dwClsContext
0x1001a476  push    [ebp+pUnkOuter]; pUnkOuter
0x1001a479  lea     eax, [ebp+rclsid]
0x1001a47c  push    eax; rclsid
0x1001a47d  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x1001a483  mov     edi, eax
0x1001a485  test    edi, edi
0x1001a487  js      short loc_1001A4FD
0x1001a489  mov     ecx, [esi]
0x1001a48b  push    ebx
0x1001a48c  push    offset __GUID_2efc7721_05da_4ac6_8300_635e373d839e
0x1001a491  push    ecx
0x1001a492  mov     eax, [ecx]
0x1001a494  mov     esi, [eax]
0x1001a496  mov     ecx, esi; this
0x1001a498  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001a49e  call    esi
0x1001a4a0  mov     edi, eax
0x1001a4a2  test    edi, edi
0x1001a4a4  js      short loc_1001A4FD
0x1001a4a6  mov     eax, [ebx]
0x1001a4a8  push    eax
0x1001a4a9  mov     ecx, [eax]
0x1001a4ab  mov     esi, [ecx+8]
0x1001a4ae  mov     ecx, esi; this
0x1001a4b0  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001a4b6  call    esi
0x1001a4b8  mov     eax, _WPP_GLOBAL_Control
0x1001a4bd  test    byte ptr [eax+1Ch], 20h
0x1001a4c1  jz      short loc_1001A4FD
0x1001a4c3  lea     eax, [ebp+var_20]
0x1001a4c6  push    eax; lpPerformanceCount
0x1001a4c7  call    ds:__imp__QueryPerformanceCounter@4; QueryPerformanceCounter(x)
0x1001a4cd  mov     edx, _WPP_GLOBAL_Control
0x1001a4d3  cmp     edx, offset _WPP_GLOBAL_Control
0x1001a4d9  jz      short loc_1001A4FD
0x1001a4db  cmp     byte ptr [edx+19h], 2
0x1001a4df  jb      short loc_1001A4FD
0x1001a4e1  mov     ecx, dword ptr [ebp+var_20]
0x1001a4e4  sub     ecx, dword ptr [ebp+PerformanceCount]
0x1001a4e7  mov     eax, dword ptr [ebp+var_20+4]
0x1001a4ea  sbb     eax, dword ptr [ebp+PerformanceCount+4]
0x1001a4ed  push    eax; int
0x1001a4ee  push    ecx; char
0x1001a4ef  push    dword ptr [edx+14h]
0x1001a4f2  push    dword ptr [edx+10h]; LoggerHandle
0x1001a4f5  push    0Ah
0x1001a4f7  pop     ecx; MessageNumber
0x1001a4f8  call    _WPP_SF_i@24; WPP_SF_i(x,x,x,x,x,x)
0x1001a4fd  mov     ecx, [ebp+var_4]
0x1001a500  mov     eax, edi
0x1001a502  pop     edi
0x1001a503  pop     esi
0x1001a504  xor     ecx, ebp; StackCookie
0x1001a506  pop     ebx
0x1001a507  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001a50c  leave
0x1001a50d  retn    8
```
