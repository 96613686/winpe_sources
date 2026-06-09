# LookForPortClock

- ea: `0x180015f2c`
- end: `0x180016078`
- name: `LookForPortClock`
- size: `332`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x18000b274`
- `0x180015b50`

## callees

- `0x1800016d0`
- `0x18001570c`
- `0x1800157dc`
- `0x180015820`
- `0x180015f2c`
- `0x180016080`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016028`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016028`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180015fc2`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180015fc2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LookForPortClock(__int64 *a1, const struct _GUID *a2)
{
  __int64 FileA; // rbx
  unsigned int v4; // edi
  __int64 v6; // [rsp+40h] [rbp-C0h] BYREF
  struct KSIDENTIFIER v7; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v8[99]; // [rsp+60h] [rbp-A0h] BYREF
  CHAR FileName[292]; // [rsp+1ECh] [rbp+ECh] BYREF

  SetupAPI::SetupAPI((SetupAPI *)v8, a2);
  if ( v8[0] && (FileA = -1, *a1 = 0, (unsigned int)SetupAPI::EnumDeviceInterfaces((SetupAPI *)v8)) )
  {
    v4 = 1;
    do
    {
      if ( v8[98] )
      {
        FileA = (__int64)CreateFileA(FileName, 0xC0000000, 0, 0, 3u, 0x40000080u, 0);
        if ( (unsigned __int64)(FileA - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          v7.Set = GUID_fedfae26_e46e_11d1_aace_0000f875ac12;
          *(&v7.Alignment + 2) = 0x100000000LL;
          v6 = 0;
          if ( (unsigned int)Property((void *)FileA, 0x18u, &v7, 8u, &v6, 0) )
            goto LABEL_10;
          CloseHandle((HANDLE)FileA);
          FileA = -1;
        }
      }
    }
    while ( (unsigned int)SetupAPI::EnumDeviceInterfaces((SetupAPI *)v8) );
    if ( FileA == -1 )
      goto LABEL_11;
LABEL_10:
    *a1 = FileA;
  }
  else
  {
LABEL_11:
    v4 = 0;
  }
  SetupAPI::~SetupAPI((SetupAPI *)v8);
  return v4;
}

```

## disassembly

```asm
0x180015f2c  push    rbp
0x180015f2e  push    rbx
0x180015f2f  push    rsi
0x180015f30  push    rdi
0x180015f31  lea     rbp, [rsp-228h]
0x180015f39  sub     rsp, 328h
0x180015f40  mov     rax, cs:__security_cookie
0x180015f47  xor     rax, rsp
0x180015f4a  mov     [rbp+240h+var_30], rax
0x180015f51  mov     rsi, rcx
0x180015f54  lea     rcx, [rsp+340h+var_2E0]; this
0x180015f59  call    ??0SetupAPI@@QEAA@PEBU_GUID@@@Z; SetupAPI::SetupAPI(_GUID const *)
0x180015f5e  nop
0x180015f5f  cmp     [rsp+340h+var_2E0], 0
0x180015f64  jz      loc_18001604F
0x180015f6a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180015f6e  mov     qword ptr [rsi], 0
0x180015f75  lea     rcx, [rsp+340h+var_2E0]; this
0x180015f7a  call    ?EnumDeviceInterfaces@SetupAPI@@QEAAHXZ; SetupAPI::EnumDeviceInterfaces(void)
0x180015f7f  test    eax, eax
0x180015f81  jz      loc_18001604F
0x180015f87  lea     edi, [rbx+2]
0x180015f8a  cmp     [rbp+240h+var_158], 0
0x180015f91  jz      loc_180016032
0x180015f97  mov     [rsp+340h+hTemplateFile], 0; hTemplateFile
0x180015fa0  mov     [rsp+340h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x180015fa8  mov     [rsp+340h+dwCreationDisposition], 3; dwCreationDisposition
0x180015fb0  xor     r9d, r9d; lpSecurityAttributes
0x180015fb3  xor     r8d, r8d; dwShareMode
0x180015fb6  mov     edx, 0C0000000h; dwDesiredAccess
0x180015fbb  lea     rcx, [rbp+240h+FileName]; lpFileName
0x180015fc2  call    cs:__imp_CreateFileA
0x180015fc8  mov     rbx, rax
0x180015fcb  lea     rcx, [rax-1]
0x180015fcf  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180015fd3  ja      short loc_180016032
0x180015fd5  movups  xmm0, xmmword ptr cs:_GUID_fedfae26_e46e_11d1_aace_0000f875ac12.Data1
0x180015fdc  movdqu  xmmword ptr [rsp+340h+var_2F8], xmm0
0x180015fe2  mov     dword ptr [rsp+340h+var_2F8+10h], 0
0x180015fea  mov     dword ptr [rsp+340h+var_2F8+14h], edi
0x180015fee  mov     [rsp+340h+var_300], 0
0x180015ff7  mov     qword ptr [rsp+340h+dwFlagsAndAttributes], 0; unsigned int *
0x180016000  lea     rax, [rsp+340h+var_300]
0x180016005  mov     qword ptr [rsp+340h+dwCreationDisposition], rax; void *
0x18001600a  mov     r9d, 8; unsigned int
0x180016010  lea     r8, [rsp+340h+var_2F8]; struct KSIDENTIFIER *
0x180016015  lea     edx, [r9+10h]; unsigned int
0x180016019  mov     rcx, rbx; void *
0x18001601c  call    ?Property@@YAHPEAXKPEAUKSIDENTIFIER@@K0PEAK@Z; Property(void *,ulong,KSIDENTIFIER *,ulong,void *,ulong *)
0x180016021  test    eax, eax
0x180016023  jnz     short loc_18001604A
0x180016025  mov     rcx, rbx; hObject
0x180016028  call    cs:__imp_CloseHandle
0x18001602e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180016032  lea     rcx, [rsp+340h+var_2E0]; this
0x180016037  call    ?EnumDeviceInterfaces@SetupAPI@@QEAAHXZ; SetupAPI::EnumDeviceInterfaces(void)
0x18001603c  test    eax, eax
0x18001603e  jnz     loc_180015F8A
0x180016044  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180016048  jz      short loc_18001604F
0x18001604a  mov     [rsi], rbx
0x18001604d  jmp     short loc_180016051
0x18001604f  xor     edi, edi
0x180016051  lea     rcx, [rsp+340h+var_2E0]; this
0x180016056  call    ??1SetupAPI@@QEAA@XZ; SetupAPI::~SetupAPI(void)
0x18001605b  mov     eax, edi
0x18001605d  mov     rcx, [rbp+240h+var_30]
0x180016064  xor     rcx, rsp; StackCookie
0x180016067  call    __security_check_cookie
0x18001606c  add     rsp, 328h
0x180016073  pop     rdi
0x180016074  pop     rsi
0x180016075  pop     rbx
0x180016076  pop     rbp
0x180016077  retn
```
