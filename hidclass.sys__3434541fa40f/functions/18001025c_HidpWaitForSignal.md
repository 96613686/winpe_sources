# HidpWaitForSignal

- ea: `0x18001025c`
- end: `0x180010422`
- name: `HidpWaitForSignal`
- size: `454`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010200`
- `0x18003b444`
- `0x18003f2b4`
- `0x180042b00`

## callees

- `0x18000f364`
- `0x18001025c`
- `0x1800231bc`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x180010296`
- `ntoskrnl!KeWaitForSingleObject` at `0x180010382`
- `ntoskrnl!KeWaitForSingleObject` at `0x180010296`
- `ntoskrnl!KeWaitForSingleObject` at `0x180010382`
- `ntoskrnl!DbgPrint` at `0x1800102d5`
- `ntoskrnl!DbgPrint` at `0x1800102d5`

## string_xrefs

- `0x1800102c1`: `\nHIDCLASS Watchdog: Thread 0x%p has been waiting %d minutes for %s to complete for FDO extension 0x%p\n`

## pseudocode

```c
NTSTATUS __fastcall HidpWaitForSignal(PVOID Object, const char *a2, _QWORD *a3)
{
  int v5; // esi
  NTSTATUS result; // eax
  int v8; // edx
  int v9; // r8d
  char v10; // bl
  int v11; // edx
  int v12; // r8d
  char v13; // r9
  int Timeout; // [rsp+20h] [rbp-68h]
  int v15; // [rsp+28h] [rbp-60h]
  int v16; // [rsp+30h] [rbp-58h]
  int v17; // [rsp+38h] [rbp-50h]
  union _LARGE_INTEGER v18; // [rsp+A8h] [rbp+20h] BYREF

  v18.QuadPart = -600000000;
  v5 = 0;
  result = KeWaitForSingleObject(Object, Executive, 0, 0, &v18);
  v10 = 1;
  while ( 1 )
  {
    v13 = result;
    if ( result != 258 )
      break;
    DbgPrint(
      "\nHIDCLASS Watchdog: Thread 0x%p has been waiting %d minutes for %s to complete for FDO extension 0x%p\n",
      KeGetCurrentThread(),
      ++v5,
      a2,
      a3);
    LOBYTE(v11) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    if ( (_BYTE)v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qqds(
        WPP_GLOBAL_Control->AttachedDevice,
        v11,
        v12,
        a3[84],
        2,
        2,
        72,
        (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
        *a3,
        (char)KeGetCurrentThread(),
        v5,
        (__int64)a2);
    }
    result = KeWaitForSingleObject(Object, Executive, 0, 0, &v18);
  }
  if ( result < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (result = HIDWORD(WPP_GLOBAL_Control->Timer), (result & 2) == 0)
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v10 = 0;
    }
    if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = v10;
      LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      return WPP_RECORDER_AND_TRACE_SF_qdqs(
               WPP_GLOBAL_Control->AttachedDevice,
               v8,
               v9,
               a3[84],
               Timeout,
               v15,
               v16,
               v17,
               *a3,
               v13,
               (char)KeGetCurrentThread(),
               (__int64)a2);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001025c  mov     r11, rsp
0x18001025f  mov     [r11+8], rbx
0x180010263  mov     [r11+10h], rbp
0x180010267  push    rsi
0x180010268  push    rdi
0x180010269  push    r12
0x18001026b  push    r13
0x18001026d  push    r14
0x18001026f  sub     rsp, 60h
0x180010273  mov     rdi, r8
0x180010276  mov     qword ptr [r11+20h], 0FFFFFFFFDC3CBA00h
0x18001027e  mov     rbp, rdx
0x180010281  lea     rax, [r11+20h]
0x180010285  xor     r8d, r8d; WaitMode
0x180010288  mov     [r11-68h], rax
0x18001028c  xor     edx, edx; WaitReason
0x18001028e  xor     esi, esi
0x180010290  xor     r9d, r9d; Alertable
0x180010293  mov     r14, rcx
0x180010296  call    cs:__imp_KeWaitForSingleObject
0x18001029d  nop     dword ptr [rax+rax+00h]
0x1800102a2  lea     ebx, [rsi+1]
0x1800102a5  lea     r12, WPP_GLOBAL_Control
0x1800102ac  lea     r13, WPP_RECORDER_INITIALIZED
0x1800102b3  jmp     loc_18001038E
0x1800102b8  mov     rdx, gs:188h
0x1800102c1  lea     rcx, Format; "\nHIDCLASS Watchdog: Thread 0x%p has be"...
0x1800102c8  add     esi, ebx
0x1800102ca  mov     [rsp+88h+Timeout], rdi
0x1800102cf  mov     r8d, esi
0x1800102d2  mov     r9, rbp
0x1800102d5  call    cs:__imp_DbgPrint
0x1800102dc  nop     dword ptr [rax+rax+00h]
0x1800102e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102e8  cmp     rcx, r12
0x1800102eb  jz      short loc_1800102FE
0x1800102ed  mov     eax, [rcx+2Ch]
0x1800102f0  test    al, 2
0x1800102f2  jz      short loc_1800102FE
0x1800102f4  cmp     byte ptr [rcx+29h], 2
0x1800102f8  jb      short loc_1800102FE
0x1800102fa  mov     dl, bl
0x1800102fc  jmp     short loc_180010300
0x1800102fe  xor     dl, dl
0x180010300  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180010307  setnz   r8b
0x18001030b  test    dl, dl
0x18001030d  jnz     short loc_180010314
0x18001030f  test    r8b, r8b
0x180010312  jz      short loc_18001036A
0x180010314  mov     rax, gs:188h
0x18001031d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010324  mov     r9, [rdi+2A0h]
0x18001032b  mov     [rsp+88h+var_30], rbp
0x180010330  mov     dword ptr [rsp+88h+var_38], esi
0x180010334  mov     rcx, [rcx+18h]
0x180010338  mov     [rsp+88h+var_40], rax
0x18001033d  mov     rax, [rdi]
0x180010340  mov     [rsp+88h+var_48], rax
0x180010345  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x18001034c  mov     [rsp+88h+var_50], rax
0x180010351  mov     [rsp+88h+var_58], 48h ; 'H'
0x180010358  mov     [rsp+88h+var_60], 2
0x180010360  mov     byte ptr [rsp+88h+Timeout], 2
0x180010365  call    WPP_RECORDER_AND_TRACE_SF_qqds
0x18001036a  lea     rax, [rsp+88h+arg_18]
0x180010372  xor     r9d, r9d; Alertable
0x180010375  xor     r8d, r8d; WaitMode
0x180010378  mov     [rsp+88h+Timeout], rax; Timeout
0x18001037d  xor     edx, edx; WaitReason
0x18001037f  mov     rcx, r14; Object
0x180010382  call    cs:__imp_KeWaitForSingleObject
0x180010389  nop     dword ptr [rax+rax+00h]
0x18001038e  mov     r9d, eax
0x180010391  cmp     eax, 102h
0x180010396  jz      loc_1800102B8
0x18001039c  test    eax, eax
0x18001039e  jns     short loc_180010408
0x1800103a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103a7  cmp     rcx, r12
0x1800103aa  jz      short loc_1800103B9
0x1800103ac  mov     eax, [rcx+2Ch]
0x1800103af  test    al, 2
0x1800103b1  jz      short loc_1800103B9
0x1800103b3  cmp     byte ptr [rcx+29h], 2
0x1800103b7  jnb     short loc_1800103BB
0x1800103b9  xor     bl, bl
0x1800103bb  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800103c2  setnz   r8b
0x1800103c6  test    bl, bl
0x1800103c8  jnz     short loc_1800103CF
0x1800103ca  test    r8b, r8b
0x1800103cd  jz      short loc_180010408
0x1800103cf  mov     rax, gs:188h
0x1800103d8  mov     dl, bl
0x1800103da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103e1  mov     [rsp+88h+var_30], rbp
0x1800103e6  mov     [rsp+88h+var_38], rax
0x1800103eb  mov     rax, [rdi]
0x1800103ee  mov     rcx, [rcx+18h]
0x1800103f2  mov     dword ptr [rsp+88h+var_40], r9d
0x1800103f7  mov     r9, [rdi+2A0h]
0x1800103fe  mov     [rsp+88h+var_48], rax
0x180010403  call    WPP_RECORDER_AND_TRACE_SF_qdqs
0x180010408  lea     r11, [rsp+88h+var_28]
0x18001040d  mov     rbx, [r11+30h]
0x180010411  mov     rbp, [r11+38h]
0x180010415  mov     rsp, r11
0x180010418  pop     r14
0x18001041a  pop     r13
0x18001041c  pop     r12
0x18001041e  pop     rdi
0x18001041f  pop     rsi
0x180010420  retn
```
