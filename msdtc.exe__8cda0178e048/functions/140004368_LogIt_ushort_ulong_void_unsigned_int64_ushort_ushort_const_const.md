# LogIt(ushort,ulong,void *,unsigned __int64,ushort,ushort const * * const)

- ea: `0x140004368`
- end: `0x1400044c5`
- name: `?LogIt@@YAXGKPEAX_KGQEAPEBG@Z`
- size: `349`
- prototype: `void __fastcall(unsigned __int16, DWORD, void *, __int64, unsigned __int16, const unsigned __int16 **const lpStrings)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400042cc`
- `0x140004640`

## callees

- `0x140004368`
- `0x140008010`

## import_xrefs

- `ADVAPI32!DeregisterEventSource` at `0x1400044aa`
- `ADVAPI32!DeregisterEventSource` at `0x1400044aa`
- `ADVAPI32!RegisterEventSourceW` at `0x140004459`
- `ADVAPI32!RegisterEventSourceW` at `0x140004459`
- `ADVAPI32!ReportEventW` at `0x1400044a1`
- `ADVAPI32!ReportEventW` at `0x1400044a1`

## pseudocode

```c
void __fastcall LogIt(
        unsigned __int16 a1,
        DWORD a2,
        void *a3,
        __int64 a4,
        unsigned __int16 a5,
        const unsigned __int16 **const lpStrings)
{
  unsigned int v6; // ebp
  WORD v8; // bx
  __int64 v9; // rdi
  HANDLE v10; // rax
  void *v11; // rdi
  __int64 v12; // [rsp+98h] [rbp+20h] BYREF

  v12 = a4;
  v6 = a1;
  if ( a2 >> 30 < 2 )
  {
    v8 = 4;
  }
  else if ( a2 >> 30 == 2 )
  {
    v8 = 2;
  }
  else
  {
    v8 = 1;
  }
  if ( g_pfnGetProcessLogger && (v12 = 0, g_pfnGetProcessLogger(&v12) >= 0) && (v9 = v12) != 0 )
  {
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, const unsigned __int16 **const, int, _QWORD, _DWORD))(*(_QWORD *)v12 + 24LL))(
      v12,
      v8,
      v6,
      a2,
      0,
      0,
      lpStrings,
      1,
      0,
      0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  else
  {
    v10 = RegisterEventSourceW(0, L"COM+");
    v11 = v10;
    if ( v10 )
    {
      ReportEventW(v10, v8, v6, a2, 0, 1u, 0, lpStrings, 0);
      DeregisterEventSource(v11);
    }
  }
}

```

## disassembly

```asm
0x140004368  mov     [rsp+arg_0], rbx
0x14000436d  mov     [rsp+arg_8], rbp
0x140004372  mov     [rsp+arg_18], r9
0x140004377  push    rsi
0x140004378  push    rdi
0x140004379  push    r15
0x14000437b  sub     rsp, 60h
0x14000437f  mov     eax, edx
0x140004381  movzx   ebp, cx
0x140004384  shr     eax, 1Eh
0x140004387  mov     esi, edx
0x140004389  mov     r15d, 1
0x14000438f  test    eax, eax
0x140004391  jz      short loc_1400043B4
0x140004393  sub     eax, r15d
0x140004396  jz      short loc_1400043B4
0x140004398  sub     eax, r15d
0x14000439b  jz      short loc_1400043AD
0x14000439d  cmp     eax, r15d
0x1400043a0  jz      short loc_1400043A8
0x1400043a2  movzx   ebx, r15w
0x1400043a6  jmp     short loc_1400043B9
0x1400043a8  mov     ebx, r15d
0x1400043ab  jmp     short loc_1400043B9
0x1400043ad  mov     ebx, 2
0x1400043b2  jmp     short loc_1400043B9
0x1400043b4  mov     ebx, 4
0x1400043b9  mov     rax, cs:?g_pfnGetProcessLogger@@3P6AJPEAX@ZEA; long (*g_pfnGetProcessLogger)(void *)
0x1400043c0  test    rax, rax
0x1400043c3  jz      loc_140004450
0x1400043c9  lea     rcx, [rsp+78h+arg_18]
0x1400043d1  mov     [rsp+78h+arg_18], 0
0x1400043dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043e2  test    eax, eax
0x1400043e4  js      short loc_140004450
0x1400043e6  mov     rdi, [rsp+78h+arg_18]
0x1400043ee  test    rdi, rdi
0x1400043f1  jz      short loc_140004450
0x1400043f3  mov     r9, [rsp+78h+arg_28]
0x1400043fb  mov     r8d, ebp
0x1400043fe  mov     rax, [rdi]
0x140004401  mov     rcx, rdi
0x140004404  mov     [rsp+78h+var_30], 0
0x14000440c  mov     [rsp+78h+lpRawData], 0
0x140004415  mov     dword ptr [rsp+78h+lpStrings], r15d
0x14000441a  mov     rax, [rax+18h]
0x14000441e  mov     qword ptr [rsp+78h+dwDataSize], r9
0x140004423  mov     r9d, esi
0x140004426  movzx   edx, bx
0x140004429  mov     qword ptr [rsp+78h+wNumStrings], 0
0x140004432  mov     dword ptr [rsp+78h+lpUserSid], 0
0x14000443a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000443f  mov     rax, [rdi]
0x140004442  mov     rcx, rdi
0x140004445  mov     rax, [rax+10h]
0x140004449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000444e  jmp     short loc_1400044B0
0x140004450  lea     rdx, aCom; "COM+"
0x140004457  xor     ecx, ecx; lpUNCServerName
0x140004459  call    cs:__imp_RegisterEventSourceW
0x14000445f  mov     rdi, rax
0x140004462  test    rax, rax
0x140004465  jz      short loc_1400044B0
0x140004467  mov     rcx, [rsp+78h+arg_28]
0x14000446f  mov     r9d, esi; dwEventID
0x140004472  mov     [rsp+78h+lpRawData], 0; lpRawData
0x14000447b  movzx   r8d, bp; wCategory
0x14000447f  mov     [rsp+78h+lpStrings], rcx; lpStrings
0x140004484  movzx   edx, bx; wType
0x140004487  mov     [rsp+78h+dwDataSize], 0; dwDataSize
0x14000448f  mov     rcx, rax; hEventLog
0x140004492  mov     [rsp+78h+wNumStrings], r15w; wNumStrings
0x140004498  mov     [rsp+78h+lpUserSid], 0; lpUserSid
0x1400044a1  call    cs:__imp_ReportEventW
0x1400044a7  mov     rcx, rdi; hEventLog
0x1400044aa  call    cs:__imp_DeregisterEventSource
0x1400044b0  lea     r11, [rsp+78h+var_18]
0x1400044b5  mov     rbx, [r11+20h]
0x1400044b9  mov     rbp, [r11+28h]
0x1400044bd  mov     rsp, r11
0x1400044c0  pop     r15
0x1400044c2  pop     rdi
0x1400044c3  pop     rsi
0x1400044c4  retn
```
