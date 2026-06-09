# DeviceLocHelper::DeviceLocHelper(_GUID *)

- ea: `0x180010e9c`
- end: `0x180010f00`
- name: `??0DeviceLocHelper@@QEAA@PEAU_GUID@@@Z`
- size: `100`
- prototype: `DeviceLocHelper *__fastcall(DeviceLocHelper *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011a34`

## callees

- `0x180010e9c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180010ed9`
- `KERNEL32!GetLastError` at `0x180010ed9`
- `DEVOBJ!DevObjCreateClassDeviceInfoList` at `0x180010eca`
- `DEVOBJ!DevObjCreateClassDeviceInfoList` at `0x180010eca`

## pseudocode

```c
DeviceLocHelper *__fastcall DeviceLocHelper::DeviceLocHelper(DeviceLocHelper *this, struct _GUID *a2)
{
  __int64 ClassDeviceInfoList; // rax
  signed int LastError; // eax

  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 0;
  ClassDeviceInfoList = DevObjCreateClassDeviceInfoList(a2, 0, 0, 0, 0);
  *(_QWORD *)this = ClassDeviceInfoList;
  if ( ClassDeviceInfoList == -1 )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2147467259;
    }
    *((_DWORD *)this + 2) = LastError;
  }
  return this;
}

```

## disassembly

```asm
0x180010e9c  push    rbx
0x180010e9e  sub     rsp, 30h
0x180010ea2  mov     rax, rdx
0x180010ea5  mov     qword ptr [rcx], 0
0x180010eac  mov     rbx, rcx
0x180010eaf  mov     dword ptr [rcx+8], 0
0x180010eb6  mov     rcx, rax
0x180010eb9  mov     [rsp+38h+var_18], 0
0x180010ec2  xor     r9d, r9d
0x180010ec5  xor     r8d, r8d
0x180010ec8  xor     edx, edx
0x180010eca  call    cs:__imp_DevObjCreateClassDeviceInfoList
0x180010ed0  mov     [rbx], rax
0x180010ed3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010ed7  jnz     short loc_180010EF7
0x180010ed9  call    cs:__imp_GetLastError
0x180010edf  test    eax, eax
0x180010ee1  jz      short loc_180010EEF
0x180010ee3  jle     short loc_180010EF4
0x180010ee5  movzx   eax, ax
0x180010ee8  or      eax, 80070000h
0x180010eed  jmp     short loc_180010EF4
0x180010eef  mov     eax, 80004005h
0x180010ef4  mov     [rbx+8], eax
0x180010ef7  mov     rax, rbx
0x180010efa  add     rsp, 30h
0x180010efe  pop     rbx
0x180010eff  retn
```
