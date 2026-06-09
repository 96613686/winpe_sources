# File::~File(void)

- ea: `0x10050e98`
- end: `0x10050f20`
- name: `??1File@@QAE@XZ`
- size: `136`
- prototype: `void __thiscall(File *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x100495ea`
- `0x1005306e`
- `0x100532cd`
- `0x10055023`

## callees

- `0x10050e98`
- `0x1005112a`
- `0x10074cbc`
- `0x10123110`
- `0x10123ca8`
- `0x10124048`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10050f0c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10050f0c`

## pseudocode

```c
void __thiscall File::~File(File *this)
{
  _DWORD v2[8]; // [esp+8h] [ebp-20h] BYREF

  v2[0] = 1;
  File::Close(this, (struct Err *)v2);
  if ( *((_DWORD *)this + 1) )
    operator delete[](*((void **)this + 1));
  if ( *((_DWORD *)this + 2) )
    operator delete[](*((void **)this + 2));
  if ( (v2[0] & 0xFFFFFFFE) != 0 )
    Err::Delete((Err *)v2);
  v2[7] = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
}

```

## disassembly

```asm
0x10050e98  mov     edi, edi
0x10050e9a  push    ebp
0x10050e9b  mov     ebp, esp
0x10050e9d  push    0FFFFFFFFh
0x10050e9f  push    offset ??1File@@QAE@XZ_SEH
0x10050ea4  mov     eax, large fs:0
0x10050eaa  push    eax
0x10050eab  sub     esp, 14h
0x10050eae  push    esi
0x10050eaf  mov     eax, ___security_cookie
0x10050eb4  xor     eax, ebp
0x10050eb6  push    eax
0x10050eb7  lea     eax, [ebp+var_C]
0x10050eba  mov     large fs:0, eax
0x10050ec0  mov     esi, ecx
0x10050ec2  lea     eax, [ebp+var_20]
0x10050ec5  mov     [ebp+var_20], 1
0x10050ecc  push    eax; struct Err *
0x10050ecd  call    ?Close@File@@QAEXAAVErr@@@Z; File::Close(Err &)
0x10050ed2  cmp     dword ptr [esi+4], 0
0x10050ed6  jz      short loc_10050EE1
0x10050ed8  push    dword ptr [esi+4]; Block
0x10050edb  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10050ee0  pop     ecx
0x10050ee1  cmp     dword ptr [esi+8], 0
0x10050ee5  jz      short loc_10050EF0
0x10050ee7  push    dword ptr [esi+8]; Block
0x10050eea  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10050eef  pop     ecx
0x10050ef0  test    [ebp+var_20], 0FFFFFFFEh
0x10050ef7  jz      short loc_10050F01
0x10050ef9  lea     ecx, [ebp+var_20]; this
0x10050efc  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x10050f01  lea     eax, [esi+18h]
0x10050f04  mov     [ebp+var_4], 0
0x10050f0b  push    eax; lpCriticalSection
0x10050f0c  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10050f12  mov     ecx, [ebp+var_C]
0x10050f15  mov     large fs:0, ecx
0x10050f1c  pop     ecx
0x10050f1d  pop     esi
0x10050f1e  leave
0x10050f1f  retn
0x10124060  jmp     ds:__imp____std_terminate
0x10125263  nop
0x10125264  nop
0x10125265  mov     edx, [esp-4+arg_4]
0x10125269  lea     eax, [edx+0Ch]
0x1012526c  mov     ecx, [edx-1Ch]
0x1012526f  xor     ecx, eax; StackCookie
0x10125271  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10125276  mov     eax, offset stru_10127A7C
0x1012527b  jmp     ___CxxFrameHandler3
```
