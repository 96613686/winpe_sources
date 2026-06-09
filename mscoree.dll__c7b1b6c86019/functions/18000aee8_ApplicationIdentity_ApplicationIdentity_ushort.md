# ApplicationIdentity::ApplicationIdentity(ushort *)

- ea: `0x18000aee8`
- end: `0x18000af85`
- name: `??0ApplicationIdentity@@QEAA@PEAG@Z`
- size: `157`
- prototype: `ApplicationIdentity *(ApplicationIdentity *__hidden this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ac2c`
- `0x180032a80`

## callees

- `0x180005468`
- `0x18000aee8`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x18000af33`
- `KERNEL32!GetFullPathNameW` at `0x18000af6c`
- `KERNEL32!GetFullPathNameW` at `0x18000af33`
- `KERNEL32!GetFullPathNameW` at `0x18000af6c`

## pseudocode

```c
ApplicationIdentity *__fastcall ApplicationIdentity::ApplicationIdentity(
        ApplicationIdentity *this,
        unsigned __int16 *a2)
{
  DWORD FullPathNameW; // eax
  DWORD v5; // ebx
  WCHAR *v6; // rax

  *((_QWORD *)this + 10) = 0;
  *((_DWORD *)this + 26) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 0;
  *(_QWORD *)this = 0;
  FullPathNameW = GetFullPathNameW(a2, 0, 0, 0);
  if ( FullPathNameW )
  {
    v5 = FullPathNameW + 1;
    v6 = (WCHAR *)operator new[](saturated_mul(FullPathNameW + 1, 2u));
    *(_QWORD *)this = v6;
    GetFullPathNameW(a2, v5, v6, (LPWSTR *)this + 1);
  }
  return this;
}

```

## disassembly

```asm
0x18000aee8  mov     [rsp+arg_0], rbx
0x18000aeed  mov     [rsp+arg_8], rsi
0x18000aef2  push    rdi
0x18000aef3  sub     rsp, 20h
0x18000aef7  xor     ebx, ebx
0x18000aef9  mov     rsi, rdx
0x18000aefc  mov     [rcx+50h], rbx
0x18000af00  mov     rdi, rcx
0x18000af03  mov     [rcx+68h], ebx
0x18000af06  xor     r9d, r9d; lpFilePart
0x18000af09  mov     [rcx+10h], rbx
0x18000af0d  xor     r8d, r8d; lpBuffer
0x18000af10  mov     [rcx+18h], rbx
0x18000af14  xor     edx, edx; nBufferLength
0x18000af16  mov     [rcx+20h], rbx
0x18000af1a  mov     [rcx+28h], rbx
0x18000af1e  mov     [rcx+30h], rbx
0x18000af22  mov     [rcx+38h], rbx
0x18000af26  mov     [rcx+40h], rbx
0x18000af2a  mov     [rcx+48h], ebx
0x18000af2d  mov     [rcx], rbx
0x18000af30  mov     rcx, rsi; lpFileName
0x18000af33  call    cs:__imp_GetFullPathNameW
0x18000af39  test    eax, eax
0x18000af3b  jz      short loc_18000AF72
0x18000af3d  lea     ebx, [rax+1]
0x18000af40  mov     eax, 2
0x18000af45  mov     ecx, ebx
0x18000af47  mul     rcx
0x18000af4a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000af51  cmovb   rax, rcx
0x18000af55  mov     rcx, rax; unsigned __int64
0x18000af58  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000af5d  lea     r9, [rdi+8]; lpFilePart
0x18000af61  mov     [rdi], rax
0x18000af64  mov     r8, rax; lpBuffer
0x18000af67  mov     edx, ebx; nBufferLength
0x18000af69  mov     rcx, rsi; lpFileName
0x18000af6c  call    cs:__imp_GetFullPathNameW
0x18000af72  mov     rbx, [rsp+28h+arg_0]
0x18000af77  mov     rax, rdi
0x18000af7a  mov     rsi, [rsp+28h+arg_8]
0x18000af7f  add     rsp, 20h
0x18000af83  pop     rdi
0x18000af84  retn
```
