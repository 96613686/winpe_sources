# CThumbnailRequest::_StartThreadAndWaitForThumbnail(ushort const *,ushort const *,bool)

- ea: `0x180021d08`
- end: `0x180021d95`
- name: `?_StartThreadAndWaitForThumbnail@CThumbnailRequest@@AEAAJPEBG0_N@Z`
- size: `141`
- prototype: `__int64 __fastcall(CThumbnailRequest *__hidden this, const unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020ca0`
- `0x180020d40`

## callees

- `0x18001a2f8`
- `0x180021d08`

## import_xrefs

- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180021d71`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180021d71`

## pseudocode

```c
__int64 __fastcall CThumbnailRequest::_StartThreadAndWaitForThumbnail(
        CThumbnailRequest *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4)
{
  __int64 result; // rax

  if ( !a2 )
  {
    if ( !a3 )
      return 2147942487LL;
    goto LABEL_6;
  }
  result = _AllocString<CTCoAllocPolicy>(this, a2, a2, (char *)this + 64);
  if ( (int)result < 0 )
    return result;
  if ( a3 )
  {
LABEL_6:
    result = _AllocString<CTCoAllocPolicy>(this, a2, a3, (char *)this + 72);
    if ( (int)result < 0 )
      return result;
  }
  *((_BYTE *)this + 40) = a4;
  if ( SHCreateThread(
         CContentDirectoryTransfer::EnterFolder,
         this,
         0x228u,
         CThumbnailRequest::GetThumbnailProviderForURLThreadProc) )
  {
    return *((unsigned int *)this + 6);
  }
  else
  {
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180021d08  mov     [rsp+arg_0], rbx
0x180021d0d  mov     [rsp+arg_8], rsi
0x180021d12  push    rdi
0x180021d13  sub     rsp, 20h
0x180021d17  mov     sil, r9b
0x180021d1a  mov     rdi, r8
0x180021d1d  mov     rbx, rcx
0x180021d20  test    rdx, rdx
0x180021d23  jnz     short loc_180021D31
0x180021d25  test    r8, r8
0x180021d28  jnz     short loc_180021D46
0x180021d2a  mov     eax, 80070057h
0x180021d2f  jmp     short loc_180021D85
0x180021d31  lea     r9, [rcx+40h]
0x180021d35  mov     r8, rdx
0x180021d38  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180021d3d  test    eax, eax
0x180021d3f  js      short loc_180021D85
0x180021d41  test    rdi, rdi
0x180021d44  jz      short loc_180021D56
0x180021d46  lea     r9, [rbx+48h]
0x180021d4a  mov     r8, rdi
0x180021d4d  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180021d52  test    eax, eax
0x180021d54  js      short loc_180021D85
0x180021d56  lea     r9, ?GetThumbnailProviderForURLThreadProc@CThumbnailRequest@@CAKPEAX@Z; pfnCallback
0x180021d5d  mov     [rbx+28h], sil
0x180021d61  mov     r8d, 228h; flags
0x180021d67  lea     rcx, ?EnterFolder@CContentDirectoryTransfer@@UEAAJPEAUIShellItem@@@Z; pfnThreadProc
0x180021d6e  mov     rdx, rbx; pData
0x180021d71  call    cs:__imp_SHCreateThread
0x180021d77  test    eax, eax
0x180021d79  jz      short loc_180021D80
0x180021d7b  mov     eax, [rbx+18h]
0x180021d7e  jmp     short loc_180021D85
0x180021d80  mov     eax, 80004005h
0x180021d85  mov     rbx, [rsp+28h+arg_0]
0x180021d8a  mov     rsi, [rsp+28h+arg_8]
0x180021d8f  add     rsp, 20h
0x180021d93  pop     rdi
0x180021d94  retn
```
