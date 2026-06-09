# KsProxyCameraAccessHandler::Close(void)

- ea: `0x10037780`
- end: `0x100377c7`
- name: `?Close@KsProxyCameraAccessHandler@@UAGJXZ`
- size: `71`
- prototype: `int(KsProxyCameraAccessHandler *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x100075ad`
- `0x10037780`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x100377b9`
- `KERNEL32!LeaveCriticalSection` at `0x100377b9`
- `KERNEL32!EnterCriticalSection` at `0x1003778e`
- `KERNEL32!EnterCriticalSection` at `0x1003778e`

## string_xrefs

- `0x100377a3`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\ksproxycameraaccesshandler.cpp`

## pseudocode

```c
int __stdcall KsProxyCameraAccessHandler::Close(KsProxyCameraAccessHandler *this)
{
  int v1; // esi
  unsigned int v3; // [esp+0h] [ebp-8h]
  const char *v4; // [esp+4h] [ebp-4h]
  int savedregs; // [esp+8h] [ebp+0h]

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( *((_DWORD *)this + 3) )
  {
    v1 = 0;
  }
  else
  {
    v1 = -2147483634;
    wil::details::in1diag3::Return_Hr(
      (wil::details::in1diag3 *)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\ksproxycameraaccesshandler.cpp",
      (void *)0x8000000E,
      v3,
      v4,
      savedregs);
  }
  if ( this != (KsProxyCameraAccessHandler *)-16 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return v1;
}

```

## disassembly

```asm
0x10037780  mov     edi, edi
0x10037782  push    ebp; int
0x10037783  mov     ebp, esp
0x10037785  push    esi; char *
0x10037786  mov     esi, [ebp+this]
0x10037789  push    edi; unsigned int
0x1003778a  lea     edi, [esi+10h]
0x1003778d  push    edi; lpCriticalSection
0x1003778e  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10037794  cmp     dword ptr [esi+0Ch], 0
0x10037798  jnz     short loc_100377B2
0x1003779a  mov     ecx, [ebp+4]
0x1003779d  mov     esi, 8000000Eh
0x100377a2  push    esi; void *
0x100377a3  push    offset aMultimediaDsho_2; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x100377a8  push    46h ; 'F'
0x100377aa  pop     edx
0x100377ab  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x100377b0  jmp     short loc_100377B4
0x100377b2  xor     esi, esi
0x100377b4  test    edi, edi
0x100377b6  jz      short loc_100377BF
0x100377b8  push    edi; lpCriticalSection
0x100377b9  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100377bf  pop     edi
0x100377c0  mov     eax, esi
0x100377c2  pop     esi
0x100377c3  pop     ebp
0x100377c4  retn    4
```
