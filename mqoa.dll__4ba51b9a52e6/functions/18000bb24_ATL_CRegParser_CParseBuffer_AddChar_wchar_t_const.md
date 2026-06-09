# ATL::CRegParser::CParseBuffer::AddChar(wchar_t const *)

- ea: `0x18000bb24`
- end: `0x18000bb92`
- name: `?AddChar@CParseBuffer@CRegParser@ATL@@QEAAHPEB_W@Z`
- size: `110`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800100cc`

## callees

- `0x18000bb24`

## import_xrefs

- `ole32!CoTaskMemRealloc` at `0x18000bb54`
- `ole32!CoTaskMemRealloc` at `0x18000bb54`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::AddChar(ATL::CRegParser::CParseBuffer *this, const wchar_t *a2)
{
  int v4; // ecx
  LPVOID *v5; // rdi
  __int64 result; // rax
  __int64 v7; // rcx
  int v8; // eax

  v4 = *((_DWORD *)this + 1);
  v5 = (LPVOID *)((char *)this + 8);
  if ( *(_DWORD *)this + 1 > v4 )
  {
    result = (__int64)CoTaskMemRealloc(*v5, 4LL * v4);
    v7 = result;
    if ( !result )
      return result;
    v8 = *((_DWORD *)this + 1);
    *v5 = (LPVOID)v7;
    *((_DWORD *)this + 1) = 2 * v8;
  }
  result = 1;
  *((_WORD *)*v5 + (int)(*(_DWORD *)this)++) = *a2;
  return result;
}

```

## disassembly

```asm
0x18000bb24  mov     [rsp+arg_0], rbx
0x18000bb29  mov     [rsp+arg_8], rsi
0x18000bb2e  push    rdi
0x18000bb2f  sub     rsp, 20h
0x18000bb33  mov     rbx, rcx
0x18000bb36  mov     rsi, rdx
0x18000bb39  mov     ecx, [rcx+4]
0x18000bb3c  mov     eax, [rbx]
0x18000bb3e  lea     rdi, [rbx+8]
0x18000bb42  inc     eax
0x18000bb44  cmp     eax, ecx
0x18000bb46  jle     short loc_18000BB6D
0x18000bb48  lea     eax, [rcx+rcx]
0x18000bb4b  mov     rcx, [rdi]; pv
0x18000bb4e  movsxd  rdx, eax
0x18000bb51  add     rdx, rdx; cb
0x18000bb54  call    cs:__imp_CoTaskMemRealloc
0x18000bb5a  mov     rcx, rax
0x18000bb5d  test    rax, rax
0x18000bb60  jz      short loc_18000BB82
0x18000bb62  mov     eax, [rbx+4]
0x18000bb65  add     eax, eax
0x18000bb67  mov     [rdi], rcx
0x18000bb6a  mov     [rbx+4], eax
0x18000bb6d  movsxd  r8, dword ptr [rbx]
0x18000bb70  mov     eax, 1
0x18000bb75  movzx   ecx, word ptr [rsi]
0x18000bb78  mov     rdx, [rdi]
0x18000bb7b  mov     [rdx+r8*2], cx
0x18000bb80  inc     dword ptr [rbx]
0x18000bb82  mov     rbx, [rsp+28h+arg_0]
0x18000bb87  mov     rsi, [rsp+28h+arg_8]
0x18000bb8c  add     rsp, 20h
0x18000bb90  pop     rdi
0x18000bb91  retn
```
