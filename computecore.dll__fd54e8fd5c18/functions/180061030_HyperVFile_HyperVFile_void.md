# HyperVFile::HyperVFile(void)

- ea: `0x180061030`
- end: `0x180061237`
- name: `??0HyperVFile@@QEAA@XZ`
- size: `519`
- prototype: `HyperVFile *__fastcall(HyperVFile *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180095c0c`
- `0x180095d70`

## callees

- `0x1800067e4`
- `0x180007438`
- `0x180065d50`
- `0x18006e080`
- `0x18007eeb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800610b4`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800611ad`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800610b4`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800611ad`
- `RPCRT4!UuidCreate` at `0x18006109d`
- `RPCRT4!UuidCreate` at `0x18006109d`
- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x1800610e1`
- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x1800610e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HyperVFile *__fastcall HyperVFile::HyperVFile(HyperVFile *this)
{
  _QWORD *v2; // rdi
  _QWORD *v3; // rax
  struct _GUID v5; // [rsp+20h] [rbp-48h] BYREF
  struct _GUID v6; // [rsp+30h] [rbp-38h] BYREF

  *(_QWORD *)&v6.Data1 = this;
  HyperVStorage::HyperVStorage(this);
  *(_QWORD *)this = &HyperVFile::`vftable'{for `HyperVStorageServices'};
  *((_QWORD *)this + 1) = &HyperVFile::`vftable'{for `HyperVStorageOperationsInterface'};
  *((_QWORD *)this + 2) = &HyperVFile::`vftable'{for `HyperVStorageChangeTrackingInterface'};
  *((_QWORD *)this + 73) = &HyperVFile::`vftable';
  *((_DWORD *)this + 148) = 0;
  v2 = operator new(0xB0u);
  memset_0(v2, 0, 0xB0u);
  UuidCreate((UUID *)(v2 + 1));
  *v2 = &HyperVFileIo::`vftable';
  *((_DWORD *)v2 + 8) = 0;
  InitializeSRWLock((PSRWLOCK)v2 + 3);
  *(_OWORD *)(v2 + 5) = 0;
  v2[7] = 0;
  v2[8] = 7;
  *((_WORD *)v2 + 20) = 0;
  v2[9] = -1;
  v2[10] = 0;
  InitializeSListHead((PSLIST_HEADER)v2 + 6);
  v2[14] = 0;
  v2[15] = 0;
  v2[16] = 0;
  v2[17] = 0;
  v2[18] = 0;
  v2[19] = 0;
  v5 = *(struct _GUID *)(v2 + 1);
  HyperVStorageTrace::HyperVFileIo_Create(&v5);
  *((_QWORD *)this + 75) = v2;
  *((_QWORD *)this + 76) = 0;
  *((_QWORD *)this + 77) = 0;
  *((_QWORD *)this + 78) = 0;
  *((_QWORD *)this + 79) = 0;
  *((_QWORD *)this + 80) = 0;
  *((_QWORD *)this + 81) = 0;
  *((_QWORD *)this + 82) = 0;
  *((_QWORD *)this + 83) = 0;
  *((_QWORD *)this + 84) = 0;
  *((_DWORD *)this + 170) = 0;
  *((_QWORD *)this + 86) = 0;
  *((_QWORD *)this + 87) = 0;
  *((_QWORD *)this + 88) = 0;
  *((_QWORD *)this + 89) = 0;
  *((_DWORD *)this + 184) = 0;
  *((_DWORD *)this + 185) = 4096;
  *((_DWORD *)this + 186) = 1800000;
  *((_DWORD *)this + 190) = 0;
  InitializeSRWLock((PSRWLOCK)this + 94);
  *((_DWORD *)this + 192) = 0;
  *((_DWORD *)this + 193) = 1;
  *((_QWORD *)this + 97) = 0;
  *((_WORD *)this + 392) = 0;
  *((_QWORD *)this + 99) = 0;
  *((_QWORD *)this + 100) = 0;
  v3 = operator new(0x30u);
  *v3 = v3;
  v3[1] = v3;
  v3[2] = v3;
  *((_WORD *)v3 + 12) = 257;
  *((_QWORD *)this + 99) = v3;
  v5 = *(struct _GUID *)(*((_QWORD *)this + 75) + 8LL);
  v6 = *(struct _GUID *)((char *)this + 568);
  HyperVStorageTrace::HyperVFile_Create(&v6, &v5);
  return this;
}

```

## disassembly

```asm
0x180061030  push    rbx
0x180061032  push    rbp
0x180061033  push    rsi
0x180061034  push    rdi
0x180061035  sub     rsp, 48h
0x180061039  mov     rsi, rcx
0x18006103c  mov     qword ptr [rsp+68h+var_38.Data1], rcx
0x180061041  call    ??0HyperVStorage@@QEAA@XZ; HyperVStorage::HyperVStorage(void)
0x180061046  nop
0x180061047  lea     rax, ??_7HyperVFile@@6BHyperVStorageServices@@@; const HyperVFile::`vftable'{for `HyperVStorageServices'}
0x18006104e  mov     [rsi], rax
0x180061051  lea     rax, ??_7HyperVFile@@6BHyperVStorageOperationsInterface@@@; const HyperVFile::`vftable'{for `HyperVStorageOperationsInterface'}
0x180061058  mov     [rsi+8], rax
0x18006105c  lea     rax, ??_7HyperVFile@@6BHyperVStorageChangeTrackingInterface@@@; const HyperVFile::`vftable'{for `HyperVStorageChangeTrackingInterface'}
0x180061063  mov     [rsi+10h], rax
0x180061067  lea     rax, ??_7HyperVFile@@6B@; const HyperVFile::`vftable'
0x18006106e  mov     [rsi+248h], rax
0x180061075  xor     ebp, ebp
0x180061077  mov     [rsi+250h], ebp
0x18006107d  mov     ebx, 0B0h
0x180061082  mov     ecx, ebx; Size
0x180061084  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180061089  mov     rdi, rax
0x18006108c  mov     r8d, ebx; Size
0x18006108f  xor     edx, edx; Val
0x180061091  mov     rcx, rax; void *
0x180061094  call    memset_0
0x180061099  lea     rcx, [rdi+8]; Uuid
0x18006109d  call    cs:__imp_UuidCreate
0x1800610a3  lea     rax, ??_7HyperVFileIo@@6B@; const HyperVFileIo::`vftable'
0x1800610aa  mov     [rdi], rax
0x1800610ad  lea     rcx, [rdi+18h]; SRWLock
0x1800610b1  mov     [rcx+8], ebp
0x1800610b4  call    cs:__imp_InitializeSRWLock
0x1800610ba  xorps   xmm0, xmm0
0x1800610bd  movups  xmmword ptr [rdi+28h], xmm0
0x1800610c1  mov     [rdi+38h], rbp
0x1800610c5  mov     qword ptr [rdi+40h], 7
0x1800610cd  mov     [rdi+28h], bp
0x1800610d1  mov     qword ptr [rdi+48h], 0FFFFFFFFFFFFFFFFh
0x1800610d9  mov     [rdi+50h], rbp
0x1800610dd  lea     rcx, [rdi+60h]; ListHead
0x1800610e1  call    cs:__imp_InitializeSListHead
0x1800610e7  mov     [rdi+70h], rbp
0x1800610eb  mov     [rdi+78h], rbp
0x1800610ef  xor     eax, eax
0x1800610f1  mov     [rdi+80h], rax
0x1800610f8  mov     [rdi+88h], rax
0x1800610ff  mov     [rdi+90h], rbp
0x180061106  mov     [rdi+98h], rax
0x18006110d  movups  xmm0, xmmword ptr [rdi+8]
0x180061111  movdqu  xmmword ptr [rsp+68h+var_48.Data1], xmm0
0x180061117  lea     rcx, [rsp+68h+var_48]; struct _GUID
0x18006111c  call    ?HyperVFileIo_Create@HyperVStorageTrace@@SAXU_GUID@@@Z; HyperVStorageTrace::HyperVFileIo_Create(_GUID)
0x180061121  mov     [rsi+258h], rdi
0x180061128  mov     [rsi+260h], rbp
0x18006112f  mov     [rsi+268h], rbp
0x180061136  mov     [rsi+270h], rbp
0x18006113d  mov     [rsi+278h], rbp
0x180061144  mov     [rsi+280h], rbp
0x18006114b  mov     [rsi+288h], rbp
0x180061152  mov     [rsi+290h], rbp
0x180061159  mov     [rsi+298h], rbp
0x180061160  mov     [rsi+2A0h], rbp
0x180061167  mov     [rsi+2A8h], ebp
0x18006116d  mov     [rsi+2B0h], rbp
0x180061174  mov     [rsi+2B8h], rbp
0x18006117b  mov     [rsi+2C0h], rbp
0x180061182  mov     [rsi+2C8h], rbp
0x180061189  mov     [rsi+2E0h], ebp
0x18006118f  mov     dword ptr [rsi+2E4h], 1000h
0x180061199  mov     dword ptr [rsi+2E8h], 1B7740h
0x1800611a3  lea     rcx, [rsi+2F0h]; SRWLock
0x1800611aa  mov     [rcx+8], ebp
0x1800611ad  call    cs:__imp_InitializeSRWLock
0x1800611b3  mov     [rsi+300h], ebp
0x1800611b9  mov     dword ptr [rsi+304h], 1
0x1800611c3  xor     eax, eax
0x1800611c5  mov     [rsi+308h], rax
0x1800611cc  mov     [rsi+310h], bp
0x1800611d3  lea     rbx, [rsi+318h]
0x1800611da  mov     [rbx], rbp
0x1800611dd  mov     [rbx+8], rbp
0x1800611e1  lea     ecx, [rbp+30h]; Size
0x1800611e4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800611e9  mov     [rax], rax
0x1800611ec  mov     [rax+8], rax
0x1800611f0  mov     [rax+10h], rax
0x1800611f4  mov     word ptr [rax+18h], 101h
0x1800611fa  mov     [rbx], rax
0x1800611fd  mov     rcx, [rsi+258h]
0x180061204  movups  xmm0, xmmword ptr [rcx+8]
0x180061208  movdqu  xmmword ptr [rsp+68h+var_48.Data1], xmm0
0x18006120e  movups  xmm1, xmmword ptr [rsi+238h]
0x180061215  movdqu  xmmword ptr [rsp+68h+var_38.Data1], xmm1
0x18006121b  lea     rdx, [rsp+68h+var_48]; struct _GUID
0x180061220  lea     rcx, [rsp+68h+var_38]; struct _GUID
0x180061225  call    ?HyperVFile_Create@HyperVStorageTrace@@SAXU_GUID@@0@Z; HyperVStorageTrace::HyperVFile_Create(_GUID,_GUID)
0x18006122a  nop
0x18006122b  mov     rax, rsi
0x18006122e  add     rsp, 48h
0x180061232  pop     rdi
0x180061233  pop     rsi
0x180061234  pop     rbp
0x180061235  pop     rbx
0x180061236  retn
```
