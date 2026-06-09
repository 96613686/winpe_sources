# KsProxyCameraAccessHandler::Shutdown(void)

- ea: `0x100377d0`
- end: `0x10037849`
- name: `?Shutdown@KsProxyCameraAccessHandler@@UAGJXZ`
- size: `121`
- prototype: `int(KsProxyCameraAccessHandler *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1003771b`

## callees

- `0x100075ad`
- `0x1002d510`
- `0x100377d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1003783a`
- `KERNEL32!LeaveCriticalSection` at `0x1003783a`
- `KERNEL32!EnterCriticalSection` at `0x100377df`
- `KERNEL32!EnterCriticalSection` at `0x100377df`

## string_xrefs

- `0x10037806`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\ksproxycameraaccesshandler.cpp`

## pseudocode

```c
void *__stdcall KsProxyCameraAccessHandler::Shutdown(KsProxyCameraAccessHandler *this)
{
  int v1; // ecx
  void *v2; // eax
  void *v3; // esi
  int v4; // ecx
  unsigned int v6; // [esp+0h] [ebp-Ch]
  const char *v7; // [esp+4h] [ebp-8h]
  int v8; // [esp+8h] [ebp-4h]

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v1 = *((_DWORD *)this + 3);
  if ( v1 )
  {
    v2 = (void *)(*(int (__thiscall **)(_DWORD, _DWORD))(*(_DWORD *)v1 + 16))(
                   *(_DWORD *)(*(_DWORD *)v1 + 16),
                   *((_DWORD *)this + 3));
    v3 = v2;
    if ( (int)v2 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        (wil::details::in1diag3 *)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\ksproxycameraaccesshandler.cpp",
        v2,
        v6,
        v7,
        v8);
      goto LABEL_7;
    }
    v4 = *((_DWORD *)this + 3);
    *((_DWORD *)this + 3) = 0;
    if ( v4 )
      (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v4 + 8))(*(_DWORD *)(*(_DWORD *)v4 + 8), v4);
  }
  v3 = 0;
LABEL_7:
  if ( this != (KsProxyCameraAccessHandler *)-16 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return v3;
}

```

## disassembly

```asm
0x100377d0  mov     edi, edi
0x100377d2  push    ebp
0x100377d3  mov     ebp, esp
0x100377d5  push    ebx; int
0x100377d6  push    esi; char *
0x100377d7  push    edi; unsigned int
0x100377d8  mov     edi, [ebp+this]
0x100377db  lea     ebx, [edi+10h]
0x100377de  push    ebx; lpCriticalSection
0x100377df  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100377e5  mov     ecx, [edi+0Ch]
0x100377e8  test    ecx, ecx
0x100377ea  jz      short loc_10037833
0x100377ec  mov     eax, [ecx]
0x100377ee  push    ecx
0x100377ef  mov     esi, [eax+10h]
0x100377f2  mov     ecx, esi; this
0x100377f4  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100377fa  call    esi
0x100377fc  mov     esi, eax
0x100377fe  test    esi, esi
0x10037800  jns     short loc_10037815
0x10037802  mov     ecx, [ebp+4]
0x10037805  push    esi; void *
0x10037806  push    offset aMultimediaDsho_2; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x1003780b  push    52h ; 'R'
0x1003780d  pop     edx
0x1003780e  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x10037813  jmp     short loc_10037835
0x10037815  mov     ecx, [edi+0Ch]
0x10037818  mov     dword ptr [edi+0Ch], 0
0x1003781f  test    ecx, ecx
0x10037821  jz      short loc_10037833
0x10037823  mov     eax, [ecx]
0x10037825  push    ecx
0x10037826  mov     esi, [eax+8]
0x10037829  mov     ecx, esi; this
0x1003782b  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10037831  call    esi
0x10037833  xor     esi, esi
0x10037835  test    ebx, ebx
0x10037837  jz      short loc_10037840
0x10037839  push    ebx; lpCriticalSection
0x1003783a  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10037840  pop     edi
0x10037841  mov     eax, esi
0x10037843  pop     esi
0x10037844  pop     ebx
0x10037845  pop     ebp
0x10037846  retn    4
```
