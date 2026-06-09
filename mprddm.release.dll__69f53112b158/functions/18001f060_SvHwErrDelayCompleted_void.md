# SvHwErrDelayCompleted(void *)

- ea: `0x18001f060`
- end: `0x18001f1e3`
- name: `?SvHwErrDelayCompleted@@YAXPEAX@Z`
- size: `387`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180007d00`
- `0x18001f060`
- `0x18003d100`
- `0x18003d278`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001f18b`
- `KERNEL32!LeaveCriticalSection` at `0x18001f18b`
- `KERNEL32!EnterCriticalSection` at `0x18001f0f6`
- `KERNEL32!EnterCriticalSection` at `0x18001f0f6`

## string_xrefs

- `0x18001f12c`: `SvHwErrDelayCompleted: reposting listen for hPort%d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SvHwErrDelayCompleted(void *a1)
{
  struct DdmDeviceTable *Instance; // rax
  __int64 v3; // rbx
  __int64 v4; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v5; // [rsp+40h] [rbp-C8h] BYREF
  _DWORD v6[10]; // [rsp+50h] [rbp-B8h] BYREF
  int v7; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v8[2044]; // [rsp+7Ch] [rbp-8Ch] BYREF

  v7 = 0;
  memset_0(v8, 0, sizeof(v8));
  memset(v6, 0, sizeof(v6));
  v5 = 0;
  v4 = 0;
  Instance = DdmDeviceTable::GetInstance(0x11u);
  DdmDeviceTable::FindDevice(Instance, a1, &v4);
  v3 = v4;
  if ( v4 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 16));
    if ( *(_DWORD *)(v3 + 104) == 3 )
    {
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        LOWORD(v7) = 0;
        LOWORD(v6[0]) = 0;
        ConvertPortNoToString(v6, *(unsigned int *)(v3 + 96));
        FormatRRASErrorString(&v7, L"SvHwErrDelayCompleted: reposting listen for hPort%d\n", *(_QWORD *)(v3 + 96));
        if ( (byte_1800CF404 & 0x10) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceInfo,
            (unsigned int)&v7,
            (unsigned int)&v5,
            0,
            (__int64)v6);
      }
      *(_DWORD *)(v3 + 104) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 168LL))(v3);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 16));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 8), 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(__int64, __int64))v4)(v4, 1);
  }
}

```

## disassembly

```asm
0x18001f060  mov     rax, rsp
0x18001f063  mov     [rax+8], rbx
0x18001f067  mov     [rax+10h], rsi
0x18001f06b  mov     [rax+18h], rdi
0x18001f06f  push    rbp
0x18001f070  lea     rbp, [rax-788h]
0x18001f077  sub     rsp, 880h
0x18001f07e  mov     rax, cs:__security_cookie
0x18001f085  xor     rax, rsp
0x18001f088  mov     [rbp+780h+var_10], rax
0x18001f08f  mov     rbx, rcx
0x18001f092  xor     esi, esi
0x18001f094  mov     [rsp+880h+var_810], esi
0x18001f098  xor     edx, edx; Val
0x18001f09a  mov     r8d, 7FCh; Size
0x18001f0a0  lea     rcx, [rsp+880h+var_80C]; void *
0x18001f0a5  call    memset_0
0x18001f0aa  mov     dword ptr [rsp+880h+var_83C+4], esi
0x18001f0ae  xorps   xmm0, xmm0
0x18001f0b1  xor     eax, eax
0x18001f0b3  movups  [rsp+880h+var_83C+8], xmm0
0x18001f0b8  movups  xmmword ptr [rsp+880h+var_82C+8], xmm0
0x18001f0bd  mov     [rsp+880h+var_814], eax
0x18001f0c1  movups  [rsp+880h+var_850+8], xmm0
0x18001f0c6  mov     qword ptr [rsp+880h+var_850], rsi
0x18001f0cb  lea     ecx, [rsi+11h]; unsigned int
0x18001f0ce  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18001f0d3  lea     r8, [rsp+880h+var_850]
0x18001f0d8  mov     rdx, rbx
0x18001f0db  mov     rcx, rax
0x18001f0de  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x18001f0e3  mov     rbx, qword ptr [rsp+880h+var_850]
0x18001f0e8  test    rbx, rbx
0x18001f0eb  jnz     short loc_18001F0F2
0x18001f0ed  jmp     loc_18001F1BA
0x18001f0f2  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001f0f6  call    cs:__imp_EnterCriticalSection
0x18001f0fd  nop     dword ptr [rax+rax+00h]
0x18001f102  cmp     dword ptr [rbx+68h], 3
0x18001f106  jnz     short loc_18001F187
0x18001f108  test    cs:byte_1800CF404, 10h
0x18001f10f  jz      short loc_18001F172
0x18001f111  mov     word ptr [rsp+880h+var_810], si
0x18001f116  mov     word ptr [rsp+880h+var_83C+4], si
0x18001f11b  mov     edx, [rbx+60h]
0x18001f11e  lea     rcx, [rsp+880h+var_83C+4]
0x18001f123  call    ConvertPortNoToString
0x18001f128  mov     r8, [rbx+60h]
0x18001f12c  lea     rdx, aSvhwerrdelayco; "SvHwErrDelayCompleted: reposting listen"...
0x18001f133  lea     rcx, [rsp+880h+var_810]
0x18001f138  call    FormatRRASErrorString
0x18001f13d  test    cs:byte_1800CF404, 10h
0x18001f144  jz      short loc_18001F172
0x18001f146  lea     rax, [rsp+880h+var_83C+4]
0x18001f14b  mov     [rsp+880h+var_858], rax
0x18001f150  mov     [rsp+880h+var_860], rsi
0x18001f155  lea     r9, [rsp+880h+var_850+8]
0x18001f15a  lea     r8, [rsp+880h+var_810]
0x18001f15f  lea     rdx, RasDdmParamTraceInfo
0x18001f166  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001f16d  call    McTemplateU0zjzz_EventWriteTransfer
0x18001f172  mov     [rbx+68h], esi
0x18001f175  mov     rax, [rbx]
0x18001f178  mov     rcx, rbx
0x18001f17b  mov     rax, [rax+0A8h]
0x18001f182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f187  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001f18b  call    cs:__imp_LeaveCriticalSection
0x18001f192  nop     dword ptr [rax+rax+00h]
0x18001f197  nop
0x18001f198  or      eax, 0FFFFFFFFh
0x18001f19b  lock xadd [rbx+8], eax
0x18001f1a0  cmp     eax, 1
0x18001f1a3  jnz     short loc_18001F1BA
0x18001f1a5  mov     rcx, qword ptr [rsp+880h+var_850]
0x18001f1aa  mov     rax, [rcx]
0x18001f1ad  mov     edx, 1
0x18001f1b2  mov     rax, [rax]
0x18001f1b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1ba  mov     rcx, [rbp+780h+var_10]
0x18001f1c1  xor     rcx, rsp; StackCookie
0x18001f1c4  call    __security_check_cookie
0x18001f1c9  lea     r11, [rsp+880h+var_s0]
0x18001f1d1  mov     rbx, [r11+10h]
0x18001f1d5  mov     rsi, [r11+18h]
0x18001f1d9  mov     rdi, [r11+20h]
0x18001f1dd  mov     rsp, r11
0x18001f1e0  pop     rbp
0x18001f1e1  retn
```
