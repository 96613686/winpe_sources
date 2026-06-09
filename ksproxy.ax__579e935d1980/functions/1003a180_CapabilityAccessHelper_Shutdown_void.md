# CapabilityAccessHelper::Shutdown(void)

- ea: `0x1003a180`
- end: `0x1003a204`
- name: `?Shutdown@CapabilityAccessHelper@@UAGJXZ`
- size: `132`
- prototype: `int __stdcall(CapabilityAccessHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10039dec`

## callees

- `0x100075ad`
- `0x1002d510`
- `0x1003a180`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1003a1f4`
- `KERNEL32!LeaveCriticalSection` at `0x1003a1f4`
- `KERNEL32!EnterCriticalSection` at `0x1003a197`
- `KERNEL32!EnterCriticalSection` at `0x1003a197`

## string_xrefs

- `0x1003a1cc`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\capabilityaccesshelper.cpp`

## pseudocode

```c
void *__stdcall CapabilityAccessHelper::Shutdown(CapabilityAccessHelper *this)
{
  int v1; // ecx
  void *v2; // eax
  void *v3; // esi
  unsigned int v5; // [esp+0h] [ebp-10h]
  const char *v6; // [esp+4h] [ebp-Ch]
  int v7; // [esp+8h] [ebp-8h]

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( *(_QWORD *)((char *)this + 68) )
  {
    v1 = *((_DWORD *)this + 15);
    if ( v1 )
    {
      v2 = (void *)(*(int (__thiscall **)(_DWORD, int, _DWORD, _DWORD))(*(_DWORD *)v1 + 44))(
                     *(_DWORD *)(*(_DWORD *)v1 + 44),
                     v1,
                     *((_DWORD *)this + 17),
                     *((_DWORD *)this + 18));
      v3 = v2;
      if ( (int)v2 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          (wil::details::in1diag3 *)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\capabilityaccesshelper.cpp",
          v2,
          v5,
          v6,
          v7);
        goto LABEL_7;
      }
      *((_DWORD *)this + 17) = 0;
      *((_DWORD *)this + 18) = 0;
    }
  }
  v3 = 0;
LABEL_7:
  if ( this != (CapabilityAccessHelper *)-32 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  return v3;
}

```

## disassembly

```asm
0x1003a180  mov     edi, edi
0x1003a182  push    ebp
0x1003a183  mov     ebp, esp
0x1003a185  and     esp, 0FFFFFFF8h
0x1003a188  push    ecx
0x1003a189  push    ecx; int
0x1003a18a  push    esi; char *
0x1003a18b  push    edi; unsigned int
0x1003a18c  mov     edi, [ebp+this]
0x1003a18f  lea     eax, [edi+20h]
0x1003a192  push    eax; lpCriticalSection
0x1003a193  mov     [esp+14h+lpCriticalSection], eax
0x1003a197  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1003a19d  mov     eax, [edi+44h]
0x1003a1a0  or      eax, [edi+48h]
0x1003a1a3  jz      short loc_1003A1E9
0x1003a1a5  mov     ecx, [edi+3Ch]
0x1003a1a8  test    ecx, ecx
0x1003a1aa  jz      short loc_1003A1E9
0x1003a1ac  push    dword ptr [edi+48h]
0x1003a1af  mov     eax, [ecx]
0x1003a1b1  push    dword ptr [edi+44h]
0x1003a1b4  push    ecx
0x1003a1b5  mov     esi, [eax+2Ch]
0x1003a1b8  mov     ecx, esi; this
0x1003a1ba  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1003a1c0  call    esi
0x1003a1c2  mov     esi, eax
0x1003a1c4  test    esi, esi
0x1003a1c6  jns     short loc_1003A1DB
0x1003a1c8  mov     ecx, [ebp+4]
0x1003a1cb  push    esi; void *
0x1003a1cc  push    offset aMultimediaDsho_4; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x1003a1d1  push    55h ; 'U'
0x1003a1d3  pop     edx
0x1003a1d4  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1003a1d9  jmp     short loc_1003A1EB
0x1003a1db  mov     dword ptr [edi+44h], 0
0x1003a1e2  mov     dword ptr [edi+48h], 0
0x1003a1e9  xor     esi, esi
0x1003a1eb  mov     eax, [esp+10h+lpCriticalSection]
0x1003a1ef  test    eax, eax
0x1003a1f1  jz      short loc_1003A1FA
0x1003a1f3  push    eax; lpCriticalSection
0x1003a1f4  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1003a1fa  pop     edi
0x1003a1fb  mov     eax, esi
0x1003a1fd  pop     esi
0x1003a1fe  mov     esp, ebp
0x1003a200  pop     ebp
0x1003a201  retn    4
```
