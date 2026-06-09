# ThreadProcHelper::CheckAccess(void)

- ea: `0x100381e0`
- end: `0x1003823c`
- name: `?CheckAccess@ThreadProcHelper@@UAGJXZ`
- size: `92`
- prototype: `int(ThreadProcHelper *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x100075ad`
- `0x100381e0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1003822e`
- `KERNEL32!LeaveCriticalSection` at `0x1003822e`
- `KERNEL32!EnterCriticalSection` at `0x100381ee`
- `KERNEL32!EnterCriticalSection` at `0x100381ee`

## string_xrefs

- `0x1003821b`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\threadprochelper.cpp`

## pseudocode

```c
int __stdcall ThreadProcHelper::CheckAccess(ThreadProcHelper *this)
{
  int v1; // esi
  unsigned int v3; // [esp+0h] [ebp-8h]
  const char *v4; // [esp+4h] [ebp-4h]
  int savedregs; // [esp+8h] [ebp+0h]

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 28));
  if ( *((_DWORD *)this + 14) == 1 && *((_DWORD *)this + 16) != 4 )
  {
    v1 = -2147024891;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      (wil::details::in1diag3 *)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\threadprochelper.cpp",
      (void *)v1,
      v3,
      v4,
      savedregs);
    goto LABEL_8;
  }
  if ( !*((_DWORD *)this + 15) )
  {
    v1 = -1072873822;
    goto LABEL_6;
  }
  v1 = 0;
LABEL_8:
  if ( this != (ThreadProcHelper *)-28 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 28));
  return v1;
}

```

## disassembly

```asm
0x100381e0  mov     edi, edi
0x100381e2  push    ebp; int
0x100381e3  mov     ebp, esp
0x100381e5  push    esi; char *
0x100381e6  mov     esi, [ebp+this]
0x100381e9  push    edi; unsigned int
0x100381ea  lea     edi, [esi+1Ch]
0x100381ed  push    edi; lpCriticalSection
0x100381ee  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100381f4  cmp     dword ptr [esi+38h], 1
0x100381f8  jnz     short loc_10038209
0x100381fa  cmp     dword ptr [esi+40h], 4
0x100381fe  jz      short loc_10038209
0x10038200  mov     esi, 80070005h
0x10038205  push    7Ch ; '|'
0x10038207  jmp     short loc_10038216
0x10038209  cmp     dword ptr [esi+3Ch], 0
0x1003820d  jnz     short loc_10038227
0x1003820f  mov     esi, 0C00D3EA2h
0x10038214  push    7Eh ; '~'
0x10038216  mov     ecx, [ebp+4]
0x10038219  pop     edx
0x1003821a  push    esi; void *
0x1003821b  push    offset aMultimediaDsho_3; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x10038220  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x10038225  jmp     short loc_10038229
0x10038227  xor     esi, esi
0x10038229  test    edi, edi
0x1003822b  jz      short loc_10038234
0x1003822d  push    edi; lpCriticalSection
0x1003822e  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10038234  pop     edi
0x10038235  mov     eax, esi
0x10038237  pop     esi
0x10038238  pop     ebp
0x10038239  retn    4
```
