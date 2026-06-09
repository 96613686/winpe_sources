# FrameProvider::SetResourceID(uint)

- ea: `0x18002e800`
- end: `0x18002e84b`
- name: `?SetResourceID@FrameProvider@@UEAAJI@Z`
- size: `75`
- prototype: `__int64 __fastcall(FrameProvider *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002e800`

## import_xrefs

- `DUI70!?Create@XResourceProvider@DirectUI@@SAJPEAUHINSTANCE__@@PEBG11PEAPEAV12@@Z` at `0x18002e828`
- `DUI70!?Create@XResourceProvider@DirectUI@@SAJPEAUHINSTANCE__@@PEBG11PEAPEAV12@@Z` at `0x18002e828`
- `DUI70!?Initialize@XProvider@DirectUI@@QEAAJPEAVElement@2@PEAVIXProviderCP@2@@Z` at `0x18002e83a`
- `DUI70!?Initialize@XProvider@DirectUI@@QEAAJPEAVElement@2@PEAVIXProviderCP@2@@Z` at `0x18002e83a`

## pseudocode

```c
int __fastcall FrameProvider::SetResourceID(FrameProvider *this, unsigned __int16 a2)
{
  struct DirectUI::IXProviderCP **v2; // rdi
  DirectUI::XProvider *v3; // rbx
  int result; // eax

  v2 = (struct DirectUI::IXProviderCP **)((char *)this + 584);
  v3 = (FrameProvider *)((char *)this - 40);
  result = DirectUI::XResourceProvider::Create(
             *((HINSTANCE *)this + 6),
             (const unsigned __int16 *)a2,
             (const unsigned __int16 *)this + 28,
             0,
             (struct DirectUI::XResourceProvider **)this + 73);
  if ( result >= 0 )
    return DirectUI::XProvider::Initialize(v3, 0, *v2);
  return result;
}

```

## disassembly

```asm
0x18002e800  mov     [rsp+arg_0], rbx
0x18002e805  push    rdi
0x18002e806  sub     rsp, 30h
0x18002e80a  lea     rdi, [rcx+248h]
0x18002e811  movzx   edx, dx
0x18002e814  lea     rbx, [rcx-28h]
0x18002e818  mov     [rsp+38h+var_18], rdi
0x18002e81d  lea     r8, [rcx+38h]
0x18002e821  xor     r9d, r9d
0x18002e824  mov     rcx, [rbx+58h]
0x18002e828  call    cs:__imp_?Create@XResourceProvider@DirectUI@@SAJPEAUHINSTANCE__@@PEBG11PEAPEAV12@@Z; DirectUI::XResourceProvider::Create(HINSTANCE__ *,ushort const *,ushort const *,ushort const *,DirectUI::XResourceProvider * *)
0x18002e82e  test    eax, eax
0x18002e830  js      short loc_18002E840
0x18002e832  mov     r8, [rdi]
0x18002e835  xor     edx, edx
0x18002e837  mov     rcx, rbx
0x18002e83a  call    cs:__imp_?Initialize@XProvider@DirectUI@@QEAAJPEAVElement@2@PEAVIXProviderCP@2@@Z; DirectUI::XProvider::Initialize(DirectUI::Element *,DirectUI::IXProviderCP *)
0x18002e840  mov     rbx, [rsp+38h+arg_0]
0x18002e845  add     rsp, 30h
0x18002e849  pop     rdi
0x18002e84a  retn
```
