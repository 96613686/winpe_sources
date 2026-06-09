# CMSDiscMasterObj::CMSDiscMasterObj(void)

- ea: `0x18000b1a4`
- end: `0x18000b350`
- name: `??0CMSDiscMasterObj@@QEAA@XZ`
- size: `428`
- prototype: `CMSDiscMasterObj *__fastcall(CMSDiscMasterObj *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180008784`
- `0x1800088b8`

## callees

- `0x18000b1a4`
- `0x18000c598`
- `0x180018500`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000b302`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b302`
- `KERNEL32!GetTempFileNameW` at `0x18000b2f3`
- `KERNEL32!GetTempFileNameW` at `0x18000b2f3`
- `KERNEL32!GetTempPath2W` at `0x18000b2d5`
- `KERNEL32!GetTempPath2W` at `0x18000b2d5`

## pseudocode

```c
CMSDiscMasterObj *__fastcall CMSDiscMasterObj::CMSDiscMasterObj(CMSDiscMasterObj *this)
{
  CMSDiscMasterObj *result; // rax
  WCHAR PathName[264]; // [rsp+20h] [rbp-228h] BYREF

  *((_DWORD *)this + 32) = 0;
  *(_OWORD *)((char *)this + 136) = 0;
  *(_OWORD *)((char *)this + 152) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_BYTE *)this + 176) = 0;
  *((GUID *)this + 2) = GUID_NULL;
  *((_DWORD *)this + 16) = 0;
  *((GUID *)this + 3) = GUID_NULL;
  *((_DWORD *)this + 17) = -16843010;
  *((GUID *)this + 5) = GUID_NULL;
  *((_DWORD *)this + 29) = -16843010;
  *((_DWORD *)this + 28) = 0;
  *((GUID *)this + 6) = GUID_NULL;
  *((_QWORD *)this + 24) = &CMyUpdateList::`vftable';
  *((_QWORD *)this + 25) = 0;
  *((_OWORD *)this + 13) = 0;
  *((_OWORD *)this + 14) = 0;
  *((_OWORD *)this + 15) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_OWORD *)this + 18) = 0;
  *((_OWORD *)this + 19) = 0;
  *((_OWORD *)this + 20) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 55) = 0;
  *((_QWORD *)this + 69) = 0;
  *((_QWORD *)this + 67) = 0;
  *((_DWORD *)this + 136) = 1;
  *((_QWORD *)this + 70) = 0;
  *((_OWORD *)this + 32) = 0;
  *((_QWORD *)this + 66) = 0;
  if ( (unsigned int)GetTempPath2W(260, PathName) && GetTempFileNameW(PathName, L"trk", 0, PathName) )
    *((_QWORD *)this + 69) = SysAllocString(PathName);
  *((_BYTE *)this + 353) = 0;
  CMSDiscMasterObj::InitializeSafeMembers(this);
  result = this;
  *((_QWORD *)this + 53) = 0;
  *((_BYTE *)this + 352) = 0;
  return result;
}

```

## disassembly

```asm
0x18000b1a4  mov     [rsp+arg_8], rbx
0x18000b1a9  push    rdi
0x18000b1aa  sub     rsp, 240h
0x18000b1b1  mov     rax, cs:__security_cookie
0x18000b1b8  xor     rax, rsp
0x18000b1bb  mov     [rsp+248h+var_18], rax
0x18000b1c3  mov     rbx, rcx
0x18000b1c6  lea     rdx, [rsp+248h+PathName]
0x18000b1cb  xor     edi, edi
0x18000b1cd  xorps   xmm0, xmm0
0x18000b1d0  mov     [rcx+80h], edi
0x18000b1d6  xor     eax, eax
0x18000b1d8  movups  xmmword ptr [rcx+88h], xmm0
0x18000b1df  movups  xmmword ptr [rcx+98h], xmm0
0x18000b1e6  mov     [rcx+0A8h], rax
0x18000b1ed  lea     rax, ??_7CMyUpdateList@@6B@; const CMyUpdateList::`vftable'
0x18000b1f4  mov     [rcx+0B0h], dil
0x18000b1fb  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000b202  movdqu  xmmword ptr [rcx+20h], xmm0
0x18000b207  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18000b20e  mov     [rcx+40h], edi
0x18000b211  movdqu  xmmword ptr [rcx+30h], xmm1
0x18000b216  mov     ecx, 0FEFEFEFEh
0x18000b21b  mov     [rbx+44h], ecx
0x18000b21e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000b225  movdqu  xmmword ptr [rbx+50h], xmm0
0x18000b22a  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18000b231  mov     [rbx+74h], ecx
0x18000b234  mov     ecx, 104h
0x18000b239  mov     [rbx+70h], edi
0x18000b23c  xorps   xmm0, xmm0
0x18000b23f  movdqu  xmmword ptr [rbx+60h], xmm1
0x18000b244  mov     [rbx+0C0h], rax
0x18000b24b  xor     eax, eax
0x18000b24d  mov     [rbx+0C8h], rdi
0x18000b254  movups  xmmword ptr [rbx+0D0h], xmm0
0x18000b25b  movups  xmmword ptr [rbx+0E0h], xmm0
0x18000b262  movups  xmmword ptr [rbx+0F0h], xmm0
0x18000b269  mov     [rbx+100h], rax
0x18000b270  movups  xmmword ptr [rbx+120h], xmm0
0x18000b277  movups  xmmword ptr [rbx+130h], xmm0
0x18000b27e  movups  xmmword ptr [rbx+140h], xmm0
0x18000b285  mov     [rbx+108h], rdi
0x18000b28c  mov     [rbx+110h], rdi
0x18000b293  mov     [rbx+118h], rdi
0x18000b29a  mov     [rbx+150h], rdi
0x18000b2a1  mov     [rbx+1B8h], rdi
0x18000b2a8  mov     [rbx+228h], rdi
0x18000b2af  mov     [rbx+218h], rdi
0x18000b2b6  mov     dword ptr [rbx+220h], 1
0x18000b2c0  mov     [rbx+230h], rdi
0x18000b2c7  movups  xmmword ptr [rbx+200h], xmm0
0x18000b2ce  mov     [rbx+210h], rax
0x18000b2d5  call    cs:__imp_GetTempPath2W
0x18000b2db  test    eax, eax
0x18000b2dd  jz      short loc_18000B30F
0x18000b2df  lea     r9, [rsp+248h+PathName]; lpTempFileName
0x18000b2e4  xor     r8d, r8d; uUnique
0x18000b2e7  lea     rdx, PrefixString; "trk"
0x18000b2ee  lea     rcx, [rsp+248h+PathName]; lpPathName
0x18000b2f3  call    cs:__imp_GetTempFileNameW
0x18000b2f9  test    eax, eax
0x18000b2fb  jz      short loc_18000B30F
0x18000b2fd  lea     rcx, [rsp+248h+PathName]; psz
0x18000b302  call    cs:__imp_SysAllocString
0x18000b308  mov     [rbx+228h], rax
0x18000b30f  mov     rcx, rbx; this
0x18000b312  mov     [rbx+161h], dil
0x18000b319  call    ?InitializeSafeMembers@CMSDiscMasterObj@@AEAAXXZ; CMSDiscMasterObj::InitializeSafeMembers(void)
0x18000b31e  mov     rax, rbx
0x18000b321  mov     [rbx+1A8h], rdi
0x18000b328  mov     [rbx+160h], dil
0x18000b32f  mov     rcx, [rsp+248h+var_18]
0x18000b337  xor     rcx, rsp; StackCookie
0x18000b33a  call    __security_check_cookie
0x18000b33f  mov     rbx, [rsp+248h+arg_8]
0x18000b347  add     rsp, 240h
0x18000b34e  pop     rdi
0x18000b34f  retn
```
