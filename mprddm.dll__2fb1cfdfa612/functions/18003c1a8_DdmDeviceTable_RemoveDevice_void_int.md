# DdmDeviceTable::RemoveDevice(void *,int)

- ea: `0x18003c1a8`
- end: `0x18003c389`
- name: `?RemoveDevice@DdmDeviceTable@@QEAAKPEAXH@Z`
- size: `481`
- prototype: `unsigned int __fastcall(DdmDeviceTable *__hidden this, void *Value, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180008020`
- `0x18003c390`

## callees

- `0x180007c50`
- `0x18003b7a8`
- `0x18003bd08`
- `0x18003c1a8`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x18003c239`
- `msvcrt!_itow_s` at `0x18003c2d1`
- `msvcrt!_itow_s` at `0x18003c239`
- `msvcrt!_itow_s` at `0x18003c2d1`

## string_xrefs

- `0x18003c242`: `RemoveDevice: (hport: %ld)`
- `0x18003c2da`: `RemoveDevice: device not found (hport: %ld)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DdmDeviceTable::RemoveDevice(__int64 **this, void *Value, int a3)
{
  unsigned int v7; // ebx
  void (__fastcall ***v8)(_QWORD); // rcx
  __int64 v9; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v10; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Buffer[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v12; // [rsp+4Ch] [rbp-B4h]
  __int128 v13; // [rsp+5Ch] [rbp-A4h]
  int v14; // [rsp+6Ch] [rbp-94h]
  int v15; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v16[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  *(_DWORD *)Buffer = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v10 = 0;
  v9 = 0;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v15) = 0;
    Buffer[0] = 0;
    if ( (_DWORD)Value != -1 )
      _itow_s((int)Value, Buffer, 0x14u, 10);
    FormatRRASErrorString(&v15, L"RemoveDevice: (hport: %ld)", Value);
    if ( (byte_1800C8404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v15,
        (unsigned int)&v10,
        0,
        (__int64)Buffer);
  }
  DdmDeviceTable::FindDevice(this, Value, &v9);
  if ( v9 )
  {
    v7 = DdmDeviceTable::RemoveDevice(this, &v9, a3);
    v8 = (void (__fastcall ***)(_QWORD))v9;
    if ( v9 && _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 8), 0xFFFFFFFF) == 1 && v8 )
      (**v8)(v8);
    return v7;
  }
  else
  {
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v15) = 0;
      Buffer[0] = 0;
      if ( (_DWORD)Value != -1 )
        _itow_s((int)Value, Buffer, 0x14u, 10);
      FormatRRASErrorString(&v15, L"RemoveDevice: device not found (hport: %ld)", Value);
      if ( (byte_1800C8404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v15,
          (unsigned int)&v10,
          0,
          (__int64)Buffer);
    }
    return 1168;
  }
}

```

## disassembly

```asm
0x18003c1a8  mov     [rsp-8+arg_10], rbx
0x18003c1ad  push    rbp
0x18003c1ae  push    rsi
0x18003c1af  push    rdi
0x18003c1b0  lea     rbp, [rsp-780h]
0x18003c1b8  sub     rsp, 880h
0x18003c1bf  mov     rax, cs:__security_cookie
0x18003c1c6  xor     rax, rsp
0x18003c1c9  mov     [rbp+790h+var_20], rax
0x18003c1d0  mov     esi, r8d
0x18003c1d3  mov     rbx, rdx
0x18003c1d6  mov     rdi, rcx
0x18003c1d9  xor     eax, eax
0x18003c1db  mov     [rsp+890h+var_820], eax
0x18003c1df  xor     edx, edx; Val
0x18003c1e1  mov     r8d, 7FCh; Size
0x18003c1e7  lea     rcx, [rsp+890h+var_81C]; void *
0x18003c1ec  call    memset_0
0x18003c1f1  xor     eax, eax
0x18003c1f3  mov     dword ptr [rsp+890h+Buffer], eax
0x18003c1f7  xorps   xmm0, xmm0
0x18003c1fa  movups  [rsp+890h+var_844], xmm0
0x18003c1ff  movups  [rsp+890h+var_834], xmm0
0x18003c204  mov     [rsp+890h+var_824], eax
0x18003c208  movups  [rsp+890h+var_858], xmm0
0x18003c20d  mov     [rsp+890h+var_860], rax
0x18003c212  test    cs:byte_1800C8404, 10h
0x18003c219  jz      short loc_18003C28C
0x18003c21b  mov     word ptr [rsp+890h+var_820], ax
0x18003c220  mov     [rsp+890h+Buffer], ax
0x18003c225  cmp     ebx, 0FFFFFFFFh
0x18003c228  jz      short loc_18003C23F
0x18003c22a  lea     r9d, [rax+0Ah]; Radix
0x18003c22e  lea     r8d, [rax+14h]; BufferCount
0x18003c232  lea     rdx, [rsp+890h+Buffer]; Buffer
0x18003c237  mov     ecx, ebx; Value
0x18003c239  call    cs:__imp__itow_s
0x18003c23f  mov     r8, rbx
0x18003c242  lea     rdx, aRemovedeviceHp; "RemoveDevice: (hport: %ld)"
0x18003c249  lea     rcx, [rsp+890h+var_820]
0x18003c24e  call    FormatRRASErrorString
0x18003c253  test    cs:byte_1800C8404, 10h
0x18003c25a  jz      short loc_18003C28C
0x18003c25c  lea     rax, [rsp+890h+Buffer]
0x18003c261  mov     [rsp+890h+var_868], rax
0x18003c266  mov     [rsp+890h+var_870], 0
0x18003c26f  lea     r9, [rsp+890h+var_858]
0x18003c274  lea     r8, [rsp+890h+var_820]
0x18003c279  lea     rdx, RasDdmParamTraceInfo
0x18003c280  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003c287  call    McTemplateU0zjzz_EventWriteTransfer
0x18003c28c  lea     r8, [rsp+890h+var_860]
0x18003c291  mov     rdx, rbx
0x18003c294  mov     rcx, rdi
0x18003c297  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x18003c29c  cmp     [rsp+890h+var_860], 0
0x18003c2a2  jnz     loc_18003C32C
0x18003c2a8  test    cs:byte_1800C8404, 8
0x18003c2af  jz      short loc_18003C325
0x18003c2b1  xor     eax, eax
0x18003c2b3  mov     word ptr [rsp+890h+var_820], ax
0x18003c2b8  mov     [rsp+890h+Buffer], ax
0x18003c2bd  cmp     ebx, 0FFFFFFFFh
0x18003c2c0  jz      short loc_18003C2D7
0x18003c2c2  lea     r9d, [rax+0Ah]; Radix
0x18003c2c6  lea     r8d, [rax+14h]; BufferCount
0x18003c2ca  lea     rdx, [rsp+890h+Buffer]; Buffer
0x18003c2cf  mov     ecx, ebx; Value
0x18003c2d1  call    cs:__imp__itow_s
0x18003c2d7  mov     r8, rbx
0x18003c2da  lea     rdx, aRemovedeviceDe; "RemoveDevice: device not found (hport: "...
0x18003c2e1  lea     rcx, [rsp+890h+var_820]
0x18003c2e6  call    FormatRRASErrorString
0x18003c2eb  test    cs:byte_1800C8404, 8
0x18003c2f2  jz      short loc_18003C325
0x18003c2f4  lea     rax, [rsp+890h+Buffer]
0x18003c2f9  mov     [rsp+890h+var_868], rax
0x18003c2fe  mov     [rsp+890h+var_870], 0
0x18003c307  lea     r9, [rsp+890h+var_858]
0x18003c30c  lea     r8, [rsp+890h+var_820]
0x18003c311  lea     rdx, RasDdmParamTraceError
0x18003c318  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003c31f  call    McTemplateU0zjzz_EventWriteTransfer
0x18003c324  nop
0x18003c325  mov     eax, 490h
0x18003c32a  jmp     short loc_18003C367
0x18003c32c  mov     r8d, esi
0x18003c32f  lea     rdx, [rsp+890h+var_860]
0x18003c334  mov     rcx, rdi; this
0x18003c337  call    ?RemoveDevice@DdmDeviceTable@@QEAAKAEAV?$RasObjPtr@VDdmDevice@@@@H@Z; DdmDeviceTable::RemoveDevice(RasObjPtr<DdmDevice> &,int)
0x18003c33c  mov     ebx, eax
0x18003c33e  mov     rcx, [rsp+890h+var_860]
0x18003c343  test    rcx, rcx
0x18003c346  jz      short loc_18003C365
0x18003c348  or      edx, 0FFFFFFFFh
0x18003c34b  lock xadd [rcx+8], edx
0x18003c350  cmp     edx, 1
0x18003c353  jnz     short loc_18003C365
0x18003c355  test    rcx, rcx
0x18003c358  jz      short loc_18003C365
0x18003c35a  mov     rax, [rcx]
0x18003c35d  mov     rax, [rax]
0x18003c360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c365  mov     eax, ebx
0x18003c367  mov     rcx, [rbp+790h+var_20]
0x18003c36e  xor     rcx, rsp; StackCookie
0x18003c371  call    __security_check_cookie
0x18003c376  mov     rbx, [rsp+890h+arg_10]
0x18003c37e  add     rsp, 880h
0x18003c385  pop     rdi
0x18003c386  pop     rsi
0x18003c387  pop     rbp
0x18003c388  retn
```
