# EtwpGetNextEvent(_WMI_BUFFER_HEADER *,_TRACELOG_CONTEXT *,ulong *,_ETW_EVENT_INFO *)

- ea: `0x1800110b0`
- end: `0x180011148`
- name: `?EtwpGetNextEvent@@YAEPEAU_WMI_BUFFER_HEADER@@PEAU_TRACELOG_CONTEXT@@PEAKPEAU_ETW_EVENT_INFO@@@Z`
- size: `152`
- prototype: `unsigned __int8 __fastcall(struct _WMI_BUFFER_HEADER *, struct _TRACELOG_CONTEXT *, unsigned int *, struct _ETW_EVENT_INFO *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ece4`
- `0x18000f384`
- `0x1800108d0`
- `0x180014b10`
- `0x180014e88`
- `0x18001502c`

## callees

- `0x1800110b0`
- `0x180012e48`
- `0x180016010`

## pseudocode

```c
unsigned __int8 __fastcall EtwpGetNextEvent(
        struct _WMI_BUFFER_HEADER *a1,
        struct _TRACELOG_CONTEXT *a2,
        unsigned int *a3,
        struct _ETW_EVENT_INFO *a4)
{
  unsigned int v4; // ebx
  struct _WMI_BUFFER_HEADER *i; // rsi
  unsigned int v9; // edi
  int v10; // eax
  unsigned int NextEventOffsetType; // r10d
  unsigned __int8 result; // al
  int v13; // [rsp+80h] [rbp+18h] BYREF

  v4 = *a3;
  v13 = 0;
  for ( i = a1; ; a1 = i )
  {
    NextEventOffsetType = EtwpGetNextEventOffsetType(a1, v4, &v13);
    if ( !NextEventOffsetType )
    {
LABEL_8:
      result = 0;
      goto LABEL_9;
    }
    if ( NextEventOffsetType == 13 )
    {
      v4 += v13;
      continue;
    }
    v9 = v4 + v13;
    if ( v4 + v13 > *((_DWORD *)i + 12) )
      goto LABEL_8;
    v10 = (*((__int64 (__fastcall **)(struct _TRACELOG_CONTEXT *, char *, struct _ETW_EVENT_INFO *, _QWORD, struct _WMI_BUFFER_HEADER *))a2
           + 68))(
            a2,
            (char *)i + v4,
            a4,
            NextEventOffsetType,
            i);
    v4 = v9;
    if ( !v10 )
      break;
  }
  result = 1;
LABEL_9:
  *a3 = v4;
  return result;
}

```

## disassembly

```asm
0x1800110b0  mov     rax, rsp
0x1800110b3  push    rbx
0x1800110b4  push    rbp
0x1800110b5  push    rsi
0x1800110b6  push    rdi
0x1800110b7  push    r14
0x1800110b9  push    r15
0x1800110bb  sub     rsp, 38h
0x1800110bf  mov     ebx, [r8]
0x1800110c2  mov     r15, r9
0x1800110c5  mov     r14, r8
0x1800110c8  mov     dword ptr [rax+18h], 0
0x1800110cf  mov     rbp, rdx
0x1800110d2  mov     rsi, rcx
0x1800110d5  jmp     short loc_18001111C
0x1800110d7  cmp     r10d, 0Dh
0x1800110db  jnz     short loc_1800110E6
0x1800110dd  add     ebx, [rsp+68h+arg_10]
0x1800110e4  jmp     short loc_180011119
0x1800110e6  mov     edi, [rsp+68h+arg_10]
0x1800110ed  add     edi, ebx
0x1800110ef  cmp     edi, [rsi+30h]
0x1800110f2  ja      short loc_180011132
0x1800110f4  mov     rax, [rbp+220h]
0x1800110fb  mov     r9d, r10d
0x1800110fe  mov     edx, ebx
0x180011100  mov     r8, r15
0x180011103  add     rdx, rsi
0x180011106  mov     [rsp+68h+var_48], rsi
0x18001110b  mov     rcx, rbp
0x18001110e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011113  mov     ebx, edi
0x180011115  test    eax, eax
0x180011117  jz      short loc_180011144
0x180011119  mov     rcx, rsi
0x18001111c  lea     r8, [rsp+68h+arg_10]
0x180011124  mov     edx, ebx
0x180011126  call    EtwpGetNextEventOffsetType
0x18001112b  mov     r10d, eax
0x18001112e  test    eax, eax
0x180011130  jnz     short loc_1800110D7
0x180011132  xor     al, al
0x180011134  mov     [r14], ebx
0x180011137  add     rsp, 38h
0x18001113b  pop     r15
0x18001113d  pop     r14
0x18001113f  pop     rdi
0x180011140  pop     rsi
0x180011141  pop     rbp
0x180011142  pop     rbx
0x180011143  retn
0x180011144  mov     al, 1
0x180011146  jmp     short loc_180011134
```
