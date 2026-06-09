# CRasCredential::_UpdateConnectStatus(void)

- ea: `0x1800028b8`
- end: `0x180002969`
- name: `?_UpdateConnectStatus@CRasCredential@@AEAAXXZ`
- size: `177`
- prototype: `void __fastcall(CRasCredential *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180001ee0`
- `0x180002250`
- `0x180003fa0`
- `0x180004480`
- `0x1800044b0`

## callees

- `0x1800028b8`
- `0x180005380`
- `0x18000c010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x180002910`
- `rtutils!TracePrintfExA` at `0x180002938`
- `rtutils!TracePrintfExA` at `0x180002910`
- `rtutils!TracePrintfExA` at `0x180002938`

## string_xrefs

- `0x180002909`: `CRasCredential::_UpdateConnectStatus for [%S] as Connected`
- `0x180002931`: `CRasCredential::_UpdateConnectStatus for [%S] as Disconnected`

## pseudocode

```c
void __fastcall CRasCredential::_UpdateConnectStatus(const wchar_t *this)
{
  const wchar_t *v2; // r9
  const wchar_t *v3; // [rsp+40h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 1) )
  {
    if ( *((_DWORD *)this + 135) )
    {
      v3 = 0;
      if ( (int)StringResourceStringCoAllocCopy(3000, &v3) < 0 )
        return;
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "CRasCredential::_UpdateConnectStatus for [%S] as Connected", this + 10);
      v2 = v3;
    }
    else
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "CRasCredential::_UpdateConnectStatus for [%S] as Disconnected", this + 10);
      v2 = &Data;
    }
    (*(void (__fastcall **)(_QWORD, const wchar_t *, __int64, const wchar_t *))(**((_QWORD **)this + 1) + 40LL))(
      *((_QWORD *)this + 1),
      this,
      2,
      v2);
  }
}

```

## disassembly

```asm
0x1800028b8  mov     [rsp+arg_8], rbx
0x1800028bd  push    rdi
0x1800028be  sub     rsp, 30h
0x1800028c2  cmp     qword ptr [rcx+8], 0
0x1800028c7  mov     rbx, rcx
0x1800028ca  jz      loc_18000295E
0x1800028d0  cmp     dword ptr [rcx+21Ch], 0
0x1800028d7  jz      short loc_18000291D
0x1800028d9  lea     rdx, [rsp+38h+arg_0]
0x1800028de  mov     [rsp+38h+arg_0], 0
0x1800028e7  mov     ecx, 0BB8h
0x1800028ec  call    _StringResourceStringCoAllocCopy
0x1800028f1  test    eax, eax
0x1800028f3  js      short loc_18000295E
0x1800028f5  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800028fb  cmp     ecx, 0FFFFFFFFh
0x1800028fe  jz      short loc_180002916
0x180002900  lea     r9, [rbx+14h]
0x180002904  mov     edx, 0Ch; dwFlags
0x180002909  lea     r8, aCrascredential_13; "CRasCredential::_UpdateConnectStatus fo"...
0x180002910  call    cs:__imp_TracePrintfExA
0x180002916  mov     r9, [rsp+38h+arg_0]
0x18000291b  jmp     short loc_180002945
0x18000291d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180002923  cmp     ecx, 0FFFFFFFFh
0x180002926  jz      short loc_18000293E
0x180002928  lea     r9, [rbx+14h]
0x18000292c  mov     edx, 0Ch; dwFlags
0x180002931  lea     r8, aCrascredential_7; "CRasCredential::_UpdateConnectStatus fo"...
0x180002938  call    cs:__imp_TracePrintfExA
0x18000293e  lea     r9, Data
0x180002945  mov     rcx, [rbx+8]
0x180002949  mov     r8d, 2
0x18000294f  mov     rdx, rbx
0x180002952  mov     rax, [rcx]
0x180002955  mov     rax, [rax+28h]
0x180002959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000295e  mov     rbx, [rsp+38h+arg_8]
0x180002963  add     rsp, 30h
0x180002967  pop     rdi
0x180002968  retn
```
