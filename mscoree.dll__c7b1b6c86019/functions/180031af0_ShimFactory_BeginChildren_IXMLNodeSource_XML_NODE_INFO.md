# ShimFactory::BeginChildren(IXMLNodeSource *,_XML_NODE_INFO *)

- ea: `0x180031af0`
- end: `0x180031b76`
- name: `?BeginChildren@ShimFactory@@UEAAJPEAUIXMLNodeSource@@PEAU_XML_NODE_INFO@@@Z`
- size: `134`
- prototype: `__int64 __fastcall(ShimFactory *__hidden this, struct IXMLNodeSource *, struct _XML_NODE_INFO *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180031af0`
- `0x180041a38`

## string_xrefs

- `0x180031b0a`: `configuration`

## pseudocode

```c
__int64 __fastcall ShimFactory::BeginChildren(ShimFactory *this, struct IXMLNodeSource *a2, const wchar_t **a3)
{
  if ( *((_DWORD *)this + 18) == 1 )
  {
    if ( !wcscmp(a3[2], L"configuration") )
      *((_DWORD *)this + 12) = 1;
  }
  else if ( *((_DWORD *)this + 18) == 2 && *((_DWORD *)this + 12) )
  {
    if ( !wcscmp(a3[2], L"startup") )
      *(_QWORD *)((char *)this + 52) = 1;
    if ( !wcscmp(a3[2], L"runtime") )
    {
      *((_DWORD *)this + 14) = 1;
      *((_DWORD *)this + 13) = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180031af0  mov     [rsp+arg_0], rbx
0x180031af5  push    rdi
0x180031af6  sub     rsp, 20h
0x180031afa  cmp     dword ptr [rcx+48h], 1
0x180031afe  mov     rdi, r8
0x180031b01  mov     rbx, rcx
0x180031b04  jnz     short loc_180031B23
0x180031b06  mov     rcx, [r8+10h]; String1
0x180031b0a  lea     rdx, aConfiguration; "configuration"
0x180031b11  call    wcscmp
0x180031b16  test    eax, eax
0x180031b18  jnz     short loc_180031B69
0x180031b1a  mov     dword ptr [rbx+30h], 1
0x180031b21  jmp     short loc_180031B69
0x180031b23  cmp     dword ptr [rcx+48h], 2
0x180031b27  jnz     short loc_180031B69
0x180031b29  cmp     dword ptr [rcx+30h], 0
0x180031b2d  jz      short loc_180031B69
0x180031b2f  mov     rcx, [r8+10h]; String1
0x180031b33  lea     rdx, aStartup; "startup"
0x180031b3a  call    wcscmp
0x180031b3f  test    eax, eax
0x180031b41  jnz     short loc_180031B4B
0x180031b43  mov     qword ptr [rbx+34h], 1
0x180031b4b  mov     rcx, [rdi+10h]; String1
0x180031b4f  lea     rdx, aRuntime; "runtime"
0x180031b56  call    wcscmp
0x180031b5b  test    eax, eax
0x180031b5d  jnz     short loc_180031B69
0x180031b5f  mov     dword ptr [rbx+38h], 1
0x180031b66  mov     [rbx+34h], eax
0x180031b69  mov     rbx, [rsp+28h+arg_0]
0x180031b6e  xor     eax, eax
0x180031b70  add     rsp, 20h
0x180031b74  pop     rdi
0x180031b75  retn
```
