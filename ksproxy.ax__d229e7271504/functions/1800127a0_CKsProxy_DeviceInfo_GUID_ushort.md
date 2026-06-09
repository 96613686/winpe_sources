# CKsProxy::DeviceInfo(_GUID *,ushort * *)

- ea: `0x1800127a0`
- end: `0x18001282f`
- name: `?DeviceInfo@CKsProxy@@UEAAJPEAU_GUID@@PEAPEAG@Z`
- size: `143`
- prototype: `__int64 __fastcall(CKsProxy *__hidden this, struct _GUID *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x1800127a0`
- `0x180044850`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800127ed`
- `ole32!CoTaskMemAlloc` at `0x1800127ed`

## pseudocode

```c
__int64 __fastcall CKsProxy::DeviceInfo(CKsProxy *this, struct _GUID *a2, unsigned __int16 **a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rax
  SIZE_T v8; // rsi
  unsigned __int16 *v9; // rax

  if ( *(_QWORD *)&this->m_MarshalerList.m_Cache.m_iCacheSize )
  {
    v5 = 0;
    *a2 = *(struct _GUID *)&this->m_MarshalerList.m_Cache.m_pHead;
    if ( a3 )
    {
      v6 = *(_QWORD *)&this->m_MarshalerList.m_Cache.m_iCacheSize;
      v7 = -1;
      do
        ++v7;
      while ( *(_WORD *)(v6 + 2 * v7) );
      v8 = 2 * v7 + 2;
      v9 = (unsigned __int16 *)CoTaskMemAlloc(v8);
      *a3 = v9;
      if ( v9 )
        memcpy_0(v9, *(const void **)&this->m_MarshalerList.m_Cache.m_iCacheSize, v8);
      else
        return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024894;
  }
  return v5;
}

```

## disassembly

```asm
0x1800127a0  push    rbx
0x1800127a2  push    rbp
0x1800127a3  push    rsi
0x1800127a4  push    rdi
0x1800127a5  push    r14
0x1800127a7  sub     rsp, 20h
0x1800127ab  xor     ebp, ebp
0x1800127ad  mov     r14, r8
0x1800127b0  mov     rdi, rcx
0x1800127b3  cmp     [rcx+160h], rbp
0x1800127ba  jz      short loc_180012828
0x1800127bc  mov     ebx, ebp
0x1800127be  movups  xmm0, xmmword ptr [rcx+168h]
0x1800127c5  movdqu  xmmword ptr [rdx], xmm0
0x1800127c9  test    r8, r8
0x1800127cc  jz      short loc_180012813
0x1800127ce  mov     rcx, [rcx+160h]
0x1800127d5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800127d9  inc     rax
0x1800127dc  cmp     [rcx+rax*2], bp
0x1800127e0  jnz     short loc_1800127D9
0x1800127e2  lea     rsi, ds:2[rax*2]
0x1800127ea  mov     rcx, rsi; cb
0x1800127ed  call    cs:__imp_CoTaskMemAlloc
0x1800127f4  nop     dword ptr [rax+rax+00h]
0x1800127f9  mov     [r14], rax
0x1800127fc  test    rax, rax
0x1800127ff  jz      short loc_180012821
0x180012801  mov     rdx, [rdi+160h]; Src
0x180012808  mov     r8, rsi; Size
0x18001280b  mov     rcx, rax; void *
0x18001280e  call    memcpy_0
0x180012813  mov     eax, ebx
0x180012815  add     rsp, 20h
0x180012819  pop     r14
0x18001281b  pop     rdi
0x18001281c  pop     rsi
0x18001281d  pop     rbp
0x18001281e  pop     rbx
0x18001281f  retn
0x180012821  mov     ebx, 8007000Eh
0x180012826  jmp     short loc_180012813
0x180012828  mov     ebx, 80070002h
0x18001282d  jmp     short loc_180012813
```
