# CActiveDirectoryProvider::Terminate(void)

- ea: `0x18001e7f0`
- end: `0x18001e8bf`
- name: `?Terminate@CActiveDirectoryProvider@@UEAAXXZ`
- size: `207`
- prototype: `void __fastcall(CActiveDirectoryProvider *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001e7f0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18001e8b4`
- `KERNEL32!FreeLibrary` at `0x18001e8b4`

## pseudocode

```c
void __fastcall CActiveDirectoryProvider::Terminate(CActiveDirectoryProvider *this)
{
  HMODULE v1; // rax

  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  v1 = (HMODULE)*((_QWORD *)this + 33);
  *((_QWORD *)this + 33) = 0;
  if ( v1 )
    FreeLibrary(v1);
}

```

## disassembly

```asm
0x18001e7f0  sub     rsp, 28h
0x18001e7f4  xor     edx, edx
0x18001e7f6  mov     [rcx+8], rdx
0x18001e7fa  mov     [rcx+10h], rdx
0x18001e7fe  mov     [rcx+18h], rdx
0x18001e802  mov     [rcx+28h], rdx
0x18001e806  mov     [rcx+30h], rdx
0x18001e80a  mov     [rcx+38h], rdx
0x18001e80e  mov     [rcx+40h], rdx
0x18001e812  mov     [rcx+48h], rdx
0x18001e816  mov     [rcx+50h], rdx
0x18001e81a  mov     [rcx+58h], rdx
0x18001e81e  mov     [rcx+60h], rdx
0x18001e822  mov     [rcx+68h], rdx
0x18001e826  mov     [rcx+70h], rdx
0x18001e82a  mov     [rcx+78h], rdx
0x18001e82e  mov     [rcx+80h], rdx
0x18001e835  mov     [rcx+88h], rdx
0x18001e83c  mov     [rcx+90h], rdx
0x18001e843  mov     [rcx+98h], rdx
0x18001e84a  mov     [rcx+0A0h], rdx
0x18001e851  mov     [rcx+0A8h], rdx
0x18001e858  mov     [rcx+0B0h], rdx
0x18001e85f  mov     [rcx+0B8h], rdx
0x18001e866  mov     [rcx+0C0h], rdx
0x18001e86d  mov     [rcx+0C8h], rdx
0x18001e874  mov     [rcx+0D0h], rdx
0x18001e87b  mov     [rcx+0D8h], rdx
0x18001e882  mov     [rcx+0E0h], rdx
0x18001e889  mov     [rcx+0E8h], rdx
0x18001e890  mov     [rcx+0F0h], rdx
0x18001e897  mov     [rcx+0F8h], rdx
0x18001e89e  mov     rax, [rcx+108h]
0x18001e8a5  mov     [rcx+108h], rdx
0x18001e8ac  test    rax, rax
0x18001e8af  jz      short loc_18001E8BA
0x18001e8b1  mov     rcx, rax; hLibModule
0x18001e8b4  call    cs:__imp_FreeLibrary
0x18001e8ba  add     rsp, 28h
0x18001e8be  retn
```
