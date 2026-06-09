# CKsProxy::DeviceInfo(_GUID *,ushort * *)

- ea: `0x1000e7d0`
- end: `0x1000e851`
- name: `?DeviceInfo@CKsProxy@@UAGJPAU_GUID@@PAPAG@Z`
- size: `129`
- prototype: `int __stdcall(CKsProxy *__hidden this, struct _GUID *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x1000e7d0`
- `0x1003bcf8`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1000e81b`
- `ole32!CoTaskMemAlloc` at `0x1000e81b`

## pseudocode

```c
int __stdcall CKsProxy::DeviceInfo(CKsProxy *this, struct _GUID *a2, unsigned __int16 **a3)
{
  int v3; // esi
  CBaseList::CNode *m_pLast; // ecx
  char *v5; // edx
  __int16 m_pPrev; // ax
  SIZE_T v7; // edi
  unsigned __int16 *v8; // eax

  if ( !this->m_MarshalerList.m_pLast )
    return -2147024894;
  *a2 = *(struct _GUID *)&this->m_MarshalerList.m_Count;
  v3 = 0;
  if ( a3 )
  {
    m_pLast = this->m_MarshalerList.m_pLast;
    v5 = (char *)&m_pLast->m_pPrev + 2;
    do
    {
      m_pPrev = (__int16)m_pLast->m_pPrev;
      m_pLast = (CBaseList::CNode *)((char *)m_pLast + 2);
    }
    while ( m_pPrev );
    v7 = 2 * (((char *)m_pLast - v5) >> 1) + 2;
    v8 = (unsigned __int16 *)CoTaskMemAlloc(v7);
    *a3 = v8;
    if ( v8 )
      memcpy(v8, this->m_MarshalerList.m_pLast, v7);
    else
      return -2147024882;
  }
  return v3;
}

```

## disassembly

```asm
0x1000e7d0  mov     edi, edi
0x1000e7d2  push    ebp
0x1000e7d3  mov     ebp, esp
0x1000e7d5  push    ebx
0x1000e7d6  mov     ebx, [ebp+this]
0x1000e7d9  xor     eax, eax
0x1000e7db  push    esi
0x1000e7dc  push    edi
0x1000e7dd  cmp     [ebx+0C8h], eax
0x1000e7e3  jz      short loc_1000E843
0x1000e7e5  lea     esi, [ebx+0CCh]
0x1000e7eb  mov     edi, [ebp+arg_4]
0x1000e7ee  movsd
0x1000e7ef  movsd
0x1000e7f0  movsd
0x1000e7f1  movsd
0x1000e7f2  mov     esi, eax
0x1000e7f4  cmp     [ebp+arg_8], eax
0x1000e7f7  jz      short loc_1000E848
0x1000e7f9  mov     ecx, [ebx+0C8h]
0x1000e7ff  xor     edi, edi
0x1000e801  lea     edx, [ecx+2]
0x1000e804  mov     ax, [ecx]
0x1000e807  add     ecx, 2
0x1000e80a  cmp     ax, di
0x1000e80d  jnz     short loc_1000E804
0x1000e80f  sub     ecx, edx
0x1000e811  sar     ecx, 1
0x1000e813  lea     edi, ds:2[ecx*2]
0x1000e81a  push    edi; cb
0x1000e81b  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1000e821  mov     ecx, [ebp+arg_8]
0x1000e824  mov     [ecx], eax
0x1000e826  test    eax, eax
0x1000e828  jz      short loc_1000E83C
0x1000e82a  push    edi; Size
0x1000e82b  push    dword ptr [ebx+0C8h]; Src
0x1000e831  push    eax; void *
0x1000e832  call    _memcpy
0x1000e837  add     esp, 0Ch
0x1000e83a  jmp     short loc_1000E848
0x1000e83c  mov     esi, 8007000Eh
0x1000e841  jmp     short loc_1000E848
0x1000e843  mov     esi, 80070002h
0x1000e848  pop     edi
0x1000e849  mov     eax, esi
0x1000e84b  pop     esi
0x1000e84c  pop     ebx
0x1000e84d  pop     ebp
0x1000e84e  retn    0Ch
```
