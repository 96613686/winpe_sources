# CWwanHelper::OnSignalStateChange(_GUID const &)

- ea: `0x1800189cc`
- end: `0x180018a5c`
- name: `?OnSignalStateChange@CWwanHelper@@IEAAJAEBU_GUID@@@Z`
- size: `144`
- prototype: `__int64 __fastcall(CWwanHelper *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x1800195a0`

## callees

- `0x180008d70`
- `0x180017c24`
- `0x1800189cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018a49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018a49`
- `USER32!PostMessageW` at `0x180018a3c`
- `USER32!PostMessageW` at `0x180018a3c`

## pseudocode

```c
__int64 __fastcall CWwanHelper::OnSignalStateChange(CWwanHelper *this, const struct _GUID *a2)
{
  IMalloc *v4; // rcx
  struct _GUID v5; // xmm0
  void *v6; // rbx
  LPARAM v7; // r9
  unsigned int v9; // [rsp+40h] [rbp+18h] BYREF
  LPARAM lParam; // [rsp+48h] [rbp+20h] BYREF

  v9 = 0;
  if ( (int)CWwanHelper::GetNormalizedSignalQualityWwan(this, a2, &v9) >= 0 )
  {
    lParam = 0;
    if ( (int)CTCoAllocPolicy::Alloc(v4, 1, 0x20u, (void **)&lParam) >= 0 )
    {
      v5 = *a2;
      v6 = (void *)lParam;
      v7 = lParam;
      *(struct _GUID *)lParam = v5;
      *(_DWORD *)(v7 + 16) = v9;
      *(_QWORD *)(v7 + 24) = *((_QWORD *)this + 6);
      if ( !PostMessageW(*((HWND *)this + 5), 0x8010u, 0, v7) )
        CoTaskMemFree(v6);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800189cc  mov     [rsp+arg_0], rbx
0x1800189d1  push    rdi
0x1800189d2  sub     rsp, 20h
0x1800189d6  lea     r8, [rsp+28h+arg_10]; unsigned int *
0x1800189db  mov     [rsp+28h+arg_10], 0
0x1800189e3  mov     rbx, rdx
0x1800189e6  mov     rdi, rcx
0x1800189e9  call    ?GetNormalizedSignalQualityWwan@CWwanHelper@@AEAAJAEBU_GUID@@PEAI@Z; CWwanHelper::GetNormalizedSignalQualityWwan(_GUID const &,uint *)
0x1800189ee  test    eax, eax
0x1800189f0  js      short loc_180018A4F
0x1800189f2  mov     edx, 1; unsigned int
0x1800189f7  mov     [rsp+28h+lParam], 0
0x180018a00  lea     r9, [rsp+28h+lParam]; void **
0x180018a05  lea     r8d, [rdx+1Fh]; unsigned __int64
0x180018a09  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180018a0e  test    eax, eax
0x180018a10  js      short loc_180018A4F
0x180018a12  movups  xmm0, xmmword ptr [rbx]
0x180018a15  mov     rbx, [rsp+28h+lParam]
0x180018a1a  xor     r8d, r8d; wParam
0x180018a1d  mov     r9, rbx; lParam
0x180018a20  mov     edx, 8010h; Msg
0x180018a25  movdqu  xmmword ptr [rbx], xmm0
0x180018a29  mov     eax, [rsp+28h+arg_10]
0x180018a2d  mov     [rbx+10h], eax
0x180018a30  mov     rax, [rdi+30h]
0x180018a34  mov     [rbx+18h], rax
0x180018a38  mov     rcx, [rdi+28h]; hWnd
0x180018a3c  call    cs:__imp_PostMessageW
0x180018a42  test    eax, eax
0x180018a44  jnz     short loc_180018A4F
0x180018a46  mov     rcx, rbx; pv
0x180018a49  call    cs:__imp_CoTaskMemFree
0x180018a4f  mov     rbx, [rsp+28h+arg_0]
0x180018a54  xor     eax, eax
0x180018a56  add     rsp, 20h
0x180018a5a  pop     rdi
0x180018a5b  retn
```
