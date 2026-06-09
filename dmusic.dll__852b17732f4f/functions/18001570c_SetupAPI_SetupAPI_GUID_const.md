# SetupAPI::SetupAPI(_GUID const *)

- ea: `0x18001570c`
- end: `0x1800157d3`
- name: `??0SetupAPI@@QEAA@PEBU_GUID@@@Z`
- size: `199`
- prototype: `SetupAPI *__fastcall(SetupAPI *__hidden this, const struct _GUID *)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180015f2c`
- `0x18001e0c8`

## callees

- `0x18001570c`

## import_xrefs

- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180015783`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180015783`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800157b5`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800157b5`

## pseudocode

```c
SetupAPI *__fastcall SetupAPI::SetupAPI(SetupAPI *this, const struct _GUID *a2)
{
  __int64 DeviceInfoList; // rax

  *((_QWORD *)this + 3) = -1;
  *((_QWORD *)this + 48) = (char *)this + 112;
  *((_DWORD *)this + 8) = 48;
  *((_DWORD *)this + 20) = 32;
  *((_DWORD *)this + 28) = 8;
  *((_DWORD *)this + 168) = 0;
  *(_DWORD *)this = 0;
  *((_DWORD *)this + 164) = 0;
  *(GUID *)((char *)this + 4) = GUID_6994ad04_93ef_11d0_a3cc_00a0c9223196;
  *((_DWORD *)this + 98) = 0;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  *((_QWORD *)this + 3) = DeviceInfoList;
  if ( DeviceInfoList != -1 && (unsigned int)DevObjGetClassDevs(DeviceInfoList, (char *)this + 4, 0, 18, 0, 0) )
    *(_DWORD *)this = 1;
  return this;
}

```

## disassembly

```asm
0x18001570c  mov     [rsp+arg_0], rbx
0x180015711  push    rdi
0x180015712  sub     rsp, 30h
0x180015716  lea     rax, [rcx+70h]
0x18001571a  mov     qword ptr [rcx+18h], 0FFFFFFFFFFFFFFFFh
0x180015722  mov     [rcx+180h], rax
0x180015729  mov     rbx, rcx
0x18001572c  mov     dword ptr [rcx+20h], 30h ; '0'
0x180015733  xor     r9d, r9d
0x180015736  mov     dword ptr [rcx+50h], 20h ; ' '
0x18001573d  xor     r8d, r8d
0x180015740  mov     dword ptr [rax], 8
0x180015746  xor     edx, edx
0x180015748  mov     dword ptr [rcx+2A0h], 0
0x180015752  movups  xmm0, xmmword ptr cs:_GUID_6994ad04_93ef_11d0_a3cc_00a0c9223196.Data1
0x180015759  mov     dword ptr [rcx], 0
0x18001575f  mov     dword ptr [rcx+290h], 0
0x180015769  movdqu  xmmword ptr [rcx+4], xmm0
0x18001576e  mov     dword ptr [rcx+188h], 0
0x180015778  xor     ecx, ecx
0x18001577a  mov     [rsp+38h+var_18], 0
0x180015783  call    cs:__imp_DevObjCreateDeviceInfoList
0x180015789  mov     [rbx+18h], rax
0x18001578d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015791  jz      short loc_1800157C5
0x180015793  mov     [rsp+38h+var_10], 0
0x18001579c  lea     rdx, [rbx+4]
0x1800157a0  mov     r9d, 12h
0x1800157a6  mov     [rsp+38h+var_18], 0
0x1800157af  xor     r8d, r8d
0x1800157b2  mov     rcx, rax
0x1800157b5  call    cs:__imp_DevObjGetClassDevs
0x1800157bb  test    eax, eax
0x1800157bd  jz      short loc_1800157C5
0x1800157bf  mov     dword ptr [rbx], 1
0x1800157c5  mov     rax, rbx
0x1800157c8  mov     rbx, [rsp+38h+arg_0]
0x1800157cd  add     rsp, 30h
0x1800157d1  pop     rdi
0x1800157d2  retn
```
