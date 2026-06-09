# SvHwErrDelayCompleted(void *)

- ea: `0x18001e4c0`
- end: `0x18001e64d`
- name: `?SvHwErrDelayCompleted@@YAXPEAX@Z`
- size: `397`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180007c50`
- `0x18001e4c0`
- `0x18003b7a8`
- `0x18003b8f4`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x18001e58c`
- `msvcrt!_itow_s` at `0x18001e58c`
- `KERNEL32!LeaveCriticalSection` at `0x18001e5fd`
- `KERNEL32!LeaveCriticalSection` at `0x18001e5fd`
- `KERNEL32!EnterCriticalSection` at `0x18001e552`
- `KERNEL32!EnterCriticalSection` at `0x18001e552`

## string_xrefs

- `0x18001e596`: `SvHwErrDelayCompleted: reposting listen for hPort%d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SvHwErrDelayCompleted(void *a1)
{
  struct DdmDeviceTable *Instance; // rax
  __int64 v3; // rbx
  int v4; // ecx
  __int64 v5; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v6; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Buffer[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v8; // [rsp+4Ch] [rbp-B4h]
  __int128 v9; // [rsp+5Ch] [rbp-A4h]
  int v10; // [rsp+6Ch] [rbp-94h]
  int v11; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v12[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v11 = 0;
  memset_0(v12, 0, sizeof(v12));
  *(_DWORD *)Buffer = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v6 = 0;
  v5 = 0;
  Instance = DdmDeviceTable::GetInstance(0x11u);
  DdmDeviceTable::FindDevice(Instance, a1, &v5);
  v3 = v5;
  if ( v5 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 16));
    if ( *(_DWORD *)(v3 + 104) == 3 )
    {
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        LOWORD(v11) = 0;
        Buffer[0] = 0;
        v4 = *(_DWORD *)(v3 + 96);
        if ( v4 != -1 )
          _itow_s(v4, Buffer, 0x14u, 10);
        FormatRRASErrorString(&v11, L"SvHwErrDelayCompleted: reposting listen for hPort%d\n", *(_QWORD *)(v3 + 96));
        if ( (byte_1800C8404 & 0x10) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceInfo,
            (unsigned int)&v11,
            (unsigned int)&v6,
            0,
            (__int64)Buffer);
      }
      *(_DWORD *)(v3 + 104) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 168LL))(v3);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 16));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 8), 0xFFFFFFFF) == 1 )
    {
      if ( v3 )
        (**(void (__fastcall ***)(__int64, __int64))v3)(v3, 1);
    }
  }
}

```

## disassembly

```asm
0x18001e4c0  mov     [rsp-8+arg_0], rbx
0x18001e4c5  mov     [rsp-8+arg_8], rdi
0x18001e4ca  push    rbp
0x18001e4cb  lea     rbp, [rsp-780h]
0x18001e4d3  sub     rsp, 880h
0x18001e4da  mov     rax, cs:__security_cookie
0x18001e4e1  xor     rax, rsp
0x18001e4e4  mov     [rbp+780h+var_10], rax
0x18001e4eb  mov     rbx, rcx
0x18001e4ee  xor     eax, eax
0x18001e4f0  mov     [rsp+880h+var_810], eax
0x18001e4f4  xor     edx, edx; Val
0x18001e4f6  mov     r8d, 7FCh; Size
0x18001e4fc  lea     rcx, [rsp+880h+var_80C]; void *
0x18001e501  call    memset_0
0x18001e506  xor     eax, eax
0x18001e508  mov     dword ptr [rsp+880h+Buffer], eax
0x18001e50c  xorps   xmm0, xmm0
0x18001e50f  movups  [rsp+880h+var_834], xmm0
0x18001e514  movups  [rsp+880h+var_824], xmm0
0x18001e519  mov     [rsp+880h+var_814], eax
0x18001e51d  movups  [rsp+880h+var_848], xmm0
0x18001e522  mov     [rsp+880h+var_850], rax
0x18001e527  lea     ecx, [rax+11h]; unsigned int
0x18001e52a  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18001e52f  lea     r8, [rsp+880h+var_850]
0x18001e534  mov     rdx, rbx
0x18001e537  mov     rcx, rax
0x18001e53a  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x18001e53f  mov     rbx, [rsp+880h+var_850]
0x18001e544  test    rbx, rbx
0x18001e547  jnz     short loc_18001E54E
0x18001e549  jmp     loc_18001E629
0x18001e54e  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001e552  call    cs:__imp_EnterCriticalSection
0x18001e558  cmp     dword ptr [rbx+68h], 3
0x18001e55c  jnz     loc_18001E5F9
0x18001e562  test    cs:byte_1800C8404, 10h
0x18001e569  jz      short loc_18001E5E0
0x18001e56b  xor     eax, eax
0x18001e56d  mov     word ptr [rsp+880h+var_810], ax
0x18001e572  mov     [rsp+880h+Buffer], ax
0x18001e577  mov     ecx, [rbx+60h]; Value
0x18001e57a  cmp     ecx, 0FFFFFFFFh
0x18001e57d  jz      short loc_18001E592
0x18001e57f  lea     r9d, [rax+0Ah]; Radix
0x18001e583  lea     r8d, [rax+14h]; BufferCount
0x18001e587  lea     rdx, [rsp+880h+Buffer]; Buffer
0x18001e58c  call    cs:__imp__itow_s
0x18001e592  mov     r8, [rbx+60h]
0x18001e596  lea     rdx, aSvhwerrdelayco; "SvHwErrDelayCompleted: reposting listen"...
0x18001e59d  lea     rcx, [rsp+880h+var_810]
0x18001e5a2  call    FormatRRASErrorString
0x18001e5a7  test    cs:byte_1800C8404, 10h
0x18001e5ae  jz      short loc_18001E5E0
0x18001e5b0  lea     rax, [rsp+880h+Buffer]
0x18001e5b5  mov     [rsp+880h+var_858], rax
0x18001e5ba  mov     [rsp+880h+var_860], 0
0x18001e5c3  lea     r9, [rsp+880h+var_848]
0x18001e5c8  lea     r8, [rsp+880h+var_810]
0x18001e5cd  lea     rdx, RasDdmParamTraceInfo
0x18001e5d4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001e5db  call    McTemplateU0zjzz_EventWriteTransfer
0x18001e5e0  mov     dword ptr [rbx+68h], 0
0x18001e5e7  mov     rax, [rbx]
0x18001e5ea  mov     rcx, rbx
0x18001e5ed  mov     rax, [rax+0A8h]
0x18001e5f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5f9  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001e5fd  call    cs:__imp_LeaveCriticalSection
0x18001e603  nop
0x18001e604  or      eax, 0FFFFFFFFh
0x18001e607  lock xadd [rbx+8], eax
0x18001e60c  cmp     eax, 1
0x18001e60f  jnz     short loc_18001E629
0x18001e611  test    rbx, rbx
0x18001e614  jz      short loc_18001E629
0x18001e616  mov     rax, [rbx]
0x18001e619  mov     edx, 1
0x18001e61e  mov     rcx, rbx
0x18001e621  mov     rax, [rax]
0x18001e624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e629  mov     rcx, [rbp+780h+var_10]
0x18001e630  xor     rcx, rsp; StackCookie
0x18001e633  call    __security_check_cookie
0x18001e638  lea     r11, [rsp+880h+var_s0]
0x18001e640  mov     rbx, [r11+10h]
0x18001e644  mov     rdi, [r11+18h]
0x18001e648  mov     rsp, r11
0x18001e64b  pop     rbp
0x18001e64c  retn
```
