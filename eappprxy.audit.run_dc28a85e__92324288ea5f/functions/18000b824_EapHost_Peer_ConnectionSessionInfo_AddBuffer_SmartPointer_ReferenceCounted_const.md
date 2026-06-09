# EapHost::Peer::ConnectionSessionInfo::AddBuffer(SmartPointer<ReferenceCounted> const &)

- ea: `0x18000b824`
- end: `0x18000b8b6`
- name: `?AddBuffer@ConnectionSessionInfo@Peer@EapHost@@QEAAXAEBV?$SmartPointer@VReferenceCounted@@@@@Z`
- size: `146`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800075c0`
- `0x180008850`
- `0x180008cf0`
- `0x180009230`
- `0x1800096e0`

## callees

- `0x1800030f8`
- `0x18000b824`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000b854`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000b854`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall EapHost::Peer::ConnectionSessionInfo::AddBuffer(__int64 a1, __int64 *a2)
{
  __int64 *v3; // rbx
  __int64 v4; // rdi
  _QWORD *v5; // rcx
  __int64 v6; // rax
  _QWORD *result; // rax

  v3 = (__int64 *)(a1 + 152);
  if ( *(_QWORD *)(a1 + 160) == 0xAAAAAAAAAAAAAAALL )
    std::_Xlength_error("list too long");
  v4 = *v3;
  v5 = operator new(0x18u);
  v6 = *a2;
  v5[2] = *a2;
  if ( v6 )
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
  ++v3[1];
  result = *(_QWORD **)(v4 + 8);
  *v5 = v4;
  v5[1] = result;
  *(_QWORD *)(v4 + 8) = v5;
  *result = v5;
  return result;
}

```

## disassembly

```asm
0x18000b824  mov     [rsp+arg_0], rbx
0x18000b829  mov     [rsp+arg_8], rsi
0x18000b82e  push    rdi
0x18000b82f  sub     rsp, 30h
0x18000b833  mov     rsi, rdx
0x18000b836  lea     rbx, [rcx+98h]
0x18000b83d  mov     rax, 0AAAAAAAAAAAAAAAh
0x18000b847  cmp     [rbx+8], rax
0x18000b84b  jnz     short loc_18000B861
0x18000b84d  lea     rcx, aListTooLong; "list too long"
0x18000b854  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000b861  mov     rdi, [rbx]
0x18000b864  mov     [rsp+38h+var_18], rbx
0x18000b869  mov     [rsp+38h+var_10], 0
0x18000b872  mov     ecx, 18h; dwBytes
0x18000b877  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b87c  mov     rcx, rax
0x18000b87f  mov     rax, [rsi]
0x18000b882  mov     [rcx+10h], rax
0x18000b886  test    rax, rax
0x18000b889  jz      short loc_18000B88F
0x18000b88b  lock inc dword ptr [rax+8]
0x18000b88f  inc     qword ptr [rbx+8]
0x18000b893  mov     rax, [rdi+8]
0x18000b897  mov     [rcx], rdi
0x18000b89a  mov     [rcx+8], rax
0x18000b89e  mov     [rdi+8], rcx
0x18000b8a2  mov     [rax], rcx
0x18000b8a5  mov     rbx, [rsp+38h+arg_0]
0x18000b8aa  mov     rsi, [rsp+38h+arg_8]
0x18000b8af  add     rsp, 30h
0x18000b8b3  pop     rdi
0x18000b8b4  retn
```
