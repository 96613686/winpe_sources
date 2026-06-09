# AslLogGetDefaultFlags

- ea: `0x1800170fc`
- end: `0x1800171be`
- name: `AslLogGetDefaultFlags`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016590`

## callees

- `0x18000e624`
- `0x18000eb0c`
- `0x1800170fc`

## import_xrefs

- `ntdll!ZwClose` at `0x18001715c`
- `ntdll!ZwClose` at `0x1800171a6`
- `ntdll!ZwClose` at `0x18001715c`
- `ntdll!ZwClose` at `0x1800171a6`

## string_xrefs

- `0x180017129`: `\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x18001716a`: `\OSDATA\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`

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
  if ( byte_1800268E8 )
  {
    v0 = dword_1800268E0;
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
  dword_1800268E0 = v0;
  byte_1800268E8 = 1;
  if ( v1 )
    ZwClose(v1);
  return v0;
}

```

## disassembly

```asm
0x1800170fc  mov     [rsp-8+arg_10], rbx
0x180017101  mov     [rsp-8+arg_18], rdi
0x180017106  push    rbp
0x180017107  mov     rbp, rsp
0x18001710a  sub     rsp, 30h
0x18001710e  xor     edi, edi
0x180017110  xor     ebx, ebx
0x180017112  cmp     cs:byte_1800268E8, bl
0x180017118  mov     [rbp+arg_0], edi
0x18001711b  mov     [rbp+Handle], rbx
0x18001711f  jz      short loc_180017129
0x180017121  mov     edi, cs:dword_1800268E0
0x180017127  jmp     short loc_180017191
0x180017129  lea     rdx, aSoftwareMicros; "\\Software\\Microsoft\\Windows NT\\Curr"...
0x180017130  lea     rcx, [rbp+Handle]
0x180017134  call    AslRegistryGetKey
0x180017139  mov     rbx, [rbp+Handle]
0x18001713d  test    eax, eax
0x18001713f  js      short loc_180017154
0x180017141  mov     rdx, rbx
0x180017144  lea     rcx, [rbp+arg_0]
0x180017148  call    AslRegistryGetUInt32
0x18001714d  mov     edi, [rbp+arg_0]
0x180017150  test    eax, eax
0x180017152  jns     short loc_180017191
0x180017154  test    rbx, rbx
0x180017157  jz      short loc_18001716A
0x180017159  mov     rcx, rbx; Handle
0x18001715c  call    cs:__imp_ZwClose
0x180017162  mov     [rbp+Handle], 0
0x18001716a  lea     rdx, aOsdataSoftware; "\\OSDATA\\Software\\Microsoft\\Windows "...
0x180017171  lea     rcx, [rbp+Handle]
0x180017175  call    AslRegistryGetKey
0x18001717a  mov     rbx, [rbp+Handle]
0x18001717e  test    eax, eax
0x180017180  js      short loc_180017191
0x180017182  mov     rdx, rbx
0x180017185  lea     rcx, [rbp+arg_0]
0x180017189  call    AslRegistryGetUInt32
0x18001718e  mov     edi, [rbp+arg_0]
0x180017191  mov     cs:dword_1800268E0, edi
0x180017197  mov     cs:byte_1800268E8, 1
0x18001719e  test    rbx, rbx
0x1800171a1  jz      short loc_1800171AC
0x1800171a3  mov     rcx, rbx; Handle
0x1800171a6  call    cs:__imp_ZwClose
0x1800171ac  mov     rbx, [rsp+30h+arg_10]
0x1800171b1  mov     eax, edi
0x1800171b3  mov     rdi, [rsp+30h+arg_18]
0x1800171b8  add     rsp, 30h
0x1800171bc  pop     rbp
0x1800171bd  retn
```
