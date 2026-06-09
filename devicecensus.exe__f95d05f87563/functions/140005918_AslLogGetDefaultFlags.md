# AslLogGetDefaultFlags

- ea: `0x140005918`
- end: `0x1400059da`
- name: `AslLogGetDefaultFlags`
- size: `194`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140004dd4`

## callees

- `0x140005918`
- `0x140007350`
- `0x140007838`

## import_xrefs

- `ntdll!ZwClose` at `0x140005978`
- `ntdll!ZwClose` at `0x1400059c2`
- `ntdll!ZwClose` at `0x140005978`
- `ntdll!ZwClose` at `0x1400059c2`

## string_xrefs

- `0x140005945`: `\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x140005986`: `\OSDATA\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`

## pseudocode

```c
__int64 AslLogGetDefaultFlags()
{
  unsigned int v0; // edi
  HANDLE v1; // rbx
  int Key; // eax
  int UInt32; // eax
  int v4; // eax
  unsigned int v6; // [rsp+40h] [rbp+10h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp+18h] BYREF

  v0 = 0;
  v1 = 0;
  v6 = 0;
  Handle = 0;
  if ( byte_14001C8F8 )
  {
    v0 = dword_14001C8F0;
  }
  else
  {
    Key = AslRegistryGetKey(&Handle, L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags");
    v1 = Handle;
    if ( Key < 0 || (UInt32 = AslRegistryGetUInt32(&v6, Handle), v0 = v6, UInt32 < 0) )
    {
      if ( v1 )
      {
        ZwClose(v1);
        Handle = 0;
      }
      v4 = AslRegistryGetKey(&Handle, L"\\OSDATA\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags");
      v1 = Handle;
      if ( v4 >= 0 )
      {
        AslRegistryGetUInt32(&v6, Handle);
        v0 = v6;
      }
    }
  }
  dword_14001C8F0 = v0;
  byte_14001C8F8 = 1;
  if ( v1 )
    ZwClose(v1);
  return v0;
}

```

## disassembly

```asm
0x140005918  mov     [rsp-8+arg_10], rbx
0x14000591d  mov     [rsp-8+arg_18], rdi
0x140005922  push    rbp
0x140005923  mov     rbp, rsp
0x140005926  sub     rsp, 30h
0x14000592a  xor     edi, edi
0x14000592c  xor     ebx, ebx
0x14000592e  cmp     cs:byte_14001C8F8, bl
0x140005934  mov     [rbp+arg_0], edi
0x140005937  mov     [rbp+Handle], rbx
0x14000593b  jz      short loc_140005945
0x14000593d  mov     edi, cs:dword_14001C8F0
0x140005943  jmp     short loc_1400059AD
0x140005945  lea     rdx, aSoftwareMicros_1; "\\Software\\Microsoft\\Windows NT\\Curr"...
0x14000594c  lea     rcx, [rbp+Handle]
0x140005950  call    AslRegistryGetKey
0x140005955  mov     rbx, [rbp+Handle]
0x140005959  test    eax, eax
0x14000595b  js      short loc_140005970
0x14000595d  mov     rdx, rbx
0x140005960  lea     rcx, [rbp+arg_0]
0x140005964  call    AslRegistryGetUInt32
0x140005969  mov     edi, [rbp+arg_0]
0x14000596c  test    eax, eax
0x14000596e  jns     short loc_1400059AD
0x140005970  test    rbx, rbx
0x140005973  jz      short loc_140005986
0x140005975  mov     rcx, rbx; Handle
0x140005978  call    cs:__imp_ZwClose
0x14000597e  mov     [rbp+Handle], 0
0x140005986  lea     rdx, aOsdataSoftware; "\\OSDATA\\Software\\Microsoft\\Windows "...
0x14000598d  lea     rcx, [rbp+Handle]
0x140005991  call    AslRegistryGetKey
0x140005996  mov     rbx, [rbp+Handle]
0x14000599a  test    eax, eax
0x14000599c  js      short loc_1400059AD
0x14000599e  mov     rdx, rbx
0x1400059a1  lea     rcx, [rbp+arg_0]
0x1400059a5  call    AslRegistryGetUInt32
0x1400059aa  mov     edi, [rbp+arg_0]
0x1400059ad  mov     cs:dword_14001C8F0, edi
0x1400059b3  mov     cs:byte_14001C8F8, 1
0x1400059ba  test    rbx, rbx
0x1400059bd  jz      short loc_1400059C8
0x1400059bf  mov     rcx, rbx; Handle
0x1400059c2  call    cs:__imp_ZwClose
0x1400059c8  mov     rbx, [rsp+30h+arg_10]
0x1400059cd  mov     eax, edi
0x1400059cf  mov     rdi, [rsp+30h+arg_18]
0x1400059d4  add     rsp, 30h
0x1400059d8  pop     rbp
0x1400059d9  retn
```
