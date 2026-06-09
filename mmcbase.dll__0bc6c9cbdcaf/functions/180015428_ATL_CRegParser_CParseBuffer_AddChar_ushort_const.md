# ATL::CRegParser::CParseBuffer::AddChar(ushort const *)

- ea: `0x180015428`
- end: `0x180015496`
- name: `?AddChar@CParseBuffer@CRegParser@ATL@@QEAAHPEBG@Z`
- size: `110`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001650c`

## callees

- `0x180015428`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180015458`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180015458`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::AddChar(
        ATL::CRegParser::CParseBuffer *this,
        const unsigned __int16 *a2)
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
0x180015428  mov     [rsp+arg_0], rbx
0x18001542d  mov     [rsp+arg_8], rsi
0x180015432  push    rdi
0x180015433  sub     rsp, 20h
0x180015437  mov     rbx, rcx
0x18001543a  mov     rsi, rdx
0x18001543d  mov     ecx, [rcx+4]
0x180015440  mov     eax, [rbx]
0x180015442  lea     rdi, [rbx+8]
0x180015446  inc     eax
0x180015448  cmp     eax, ecx
0x18001544a  jle     short loc_180015471
0x18001544c  lea     eax, [rcx+rcx]
0x18001544f  mov     rcx, [rdi]; pv
0x180015452  movsxd  rdx, eax
0x180015455  add     rdx, rdx; cb
0x180015458  call    cs:__imp_CoTaskMemRealloc
0x18001545e  mov     rcx, rax
0x180015461  test    rax, rax
0x180015464  jz      short loc_180015486
0x180015466  mov     eax, [rbx+4]
0x180015469  add     eax, eax
0x18001546b  mov     [rdi], rcx
0x18001546e  mov     [rbx+4], eax
0x180015471  movsxd  r8, dword ptr [rbx]
0x180015474  mov     eax, 1
0x180015479  movzx   ecx, word ptr [rsi]
0x18001547c  mov     rdx, [rdi]
0x18001547f  mov     [rdx+r8*2], cx
0x180015484  inc     dword ptr [rbx]
0x180015486  mov     rbx, [rsp+28h+arg_0]
0x18001548b  mov     rsi, [rsp+28h+arg_8]
0x180015490  add     rsp, 20h
0x180015494  pop     rdi
0x180015495  retn
```
