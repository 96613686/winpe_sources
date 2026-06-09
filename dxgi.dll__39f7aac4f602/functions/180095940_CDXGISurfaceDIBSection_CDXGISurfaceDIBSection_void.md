# CDXGISurfaceDIBSection::~CDXGISurfaceDIBSection(void)

- ea: `0x180095940`
- end: `0x180095978`
- name: `??1CDXGISurfaceDIBSection@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(CDXGISurfaceDIBSection *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180098160`
- `0x1800ca6d7`

## callees

- `0x180095940`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x18009596c`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x18009596c`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18009595a`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18009595a`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180095963`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180095963`

## pseudocode

```c
void __fastcall CDXGISurfaceDIBSection::~CDXGISurfaceDIBSection(HDC *this)
{
  HDC v2; // rcx
  HDC v3; // rdx
  HGDIOBJ v4; // rax

  v2 = *this;
  if ( v2 )
  {
    v3 = this[1];
    if ( v3 )
    {
      v4 = SelectObject(v2, v3);
      DeleteObject(v4);
    }
    DeleteDC(*this);
  }
}

```

## disassembly

```asm
0x180095940  push    rbx
0x180095942  sub     rsp, 20h
0x180095946  mov     rbx, rcx
0x180095949  mov     rcx, [rcx]; hdc
0x18009594c  test    rcx, rcx
0x18009594f  jz      short loc_180095972
0x180095951  mov     rdx, [rbx+8]; h
0x180095955  test    rdx, rdx
0x180095958  jz      short loc_180095969
0x18009595a  call    cs:__imp_SelectObject
0x180095960  mov     rcx, rax; ho
0x180095963  call    cs:__imp_DeleteObject
0x180095969  mov     rcx, [rbx]; hdc
0x18009596c  call    cs:__imp_DeleteDC
0x180095972  add     rsp, 20h
0x180095976  pop     rbx
0x180095977  retn
```
