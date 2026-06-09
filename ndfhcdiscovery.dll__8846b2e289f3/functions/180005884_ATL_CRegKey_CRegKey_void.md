# ATL::CRegKey::~CRegKey(void)

- ea: `0x180005884`
- end: `0x1800058af`
- name: `??1CRegKey@ATL@@QEAA@XZ`
- size: `43`
- prototype: `void __fastcall(ATL::CRegKey *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180013dad`
- `0x180013e63`
- `0x180013e75`
- `0x180013fa7`
- `0x180014266`
- `0x180014278`
- `0x180014308`
- `0x1800143a4`

## callees

- `0x180005884`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180005895`
- `ADVAPI32!RegCloseKey` at `0x180005895`

## pseudocode

```c
void __fastcall ATL::CRegKey::~CRegKey(HKEY *this)
{
  HKEY v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    RegCloseKey(v2);
    *this = 0;
  }
}

```

## disassembly

```asm
0x180005884  push    rbx
0x180005886  sub     rsp, 20h
0x18000588a  mov     rbx, rcx
0x18000588d  mov     rcx, [rcx]; hKey
0x180005890  test    rcx, rcx
0x180005893  jz      short loc_1800058A8
0x180005895  call    cs:__imp_RegCloseKey
0x18000589c  nop     dword ptr [rax+rax+00h]
0x1800058a1  mov     qword ptr [rbx], 0
0x1800058a8  add     rsp, 20h
0x1800058ac  pop     rbx
0x1800058ad  retn
```
