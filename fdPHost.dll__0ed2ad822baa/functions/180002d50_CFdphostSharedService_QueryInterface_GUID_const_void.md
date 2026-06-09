# CFdphostSharedService::QueryInterface(_GUID const &,void * *)

- ea: `0x180002d50`
- end: `0x180002e3d`
- name: `?QueryInterface@CFdphostSharedService@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `237`
- prototype: `__int64 __fastcall(CFdphostSharedService *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180002d50`
- `0x180002f84`
- `0x18000303c`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall CFdphostSharedService::QueryInterface(
        CFdphostSharedService *this,
        const struct _GUID *a2,
        void **a3)
{
  _BYTE *v6; // rcx
  unsigned int v7; // ebx
  int v8; // eax
  bool v9; // cf

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 17);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    v7 = -2147024809;
    goto LABEL_12;
  }
  *a3 = 0;
  if ( (*(_QWORD *)&IID_IUnknown.Data1 != *(_QWORD *)&a2->Data1 || *(_QWORD *)IID_IUnknown.Data4 != *(_QWORD *)a2->Data4)
    && (*(_QWORD *)&GUID_29d809a4_4d61_4f18_9d00_b447e42a9831.Data1 != *(_QWORD *)&a2->Data1
     || *(_QWORD *)GUID_29d809a4_4d61_4f18_9d00_b447e42a9831.Data4 != *(_QWORD *)a2->Data4) )
  {
    v6 = WPP_GLOBAL_Control;
    v7 = -2147467262;
LABEL_12:
    v8 = 0;
    v9 = v6[25] < 2u;
    goto LABEL_13;
  }
  v7 = 0;
  (*(void (__fastcall **)(CFdphostSharedService *))(*(_QWORD *)this + 8LL))(this);
  *a3 = this;
  v8 = 0;
  v6 = WPP_GLOBAL_Control;
  v9 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
LABEL_13:
  if ( v6 != (_BYTE *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v8) = !v9;
    if ( v8 )
      WPP_SF_sqd(*((_QWORD *)v6 + 2), 18);
  }
  return v7;
}

```

## disassembly

```asm
0x180002d50  push    rbx
0x180002d52  push    rbp
0x180002d53  push    rsi
0x180002d54  push    rdi
0x180002d55  sub     rsp, 38h
0x180002d59  mov     rsi, r8
0x180002d5c  mov     rbx, rdx
0x180002d5f  mov     rdi, rcx
0x180002d62  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d69  lea     rbp, WPP_GLOBAL_Control
0x180002d70  cmp     rcx, rbp
0x180002d73  jz      short loc_180002D95
0x180002d75  cmp     byte ptr [rcx+19h], 4
0x180002d79  jb      short loc_180002D95
0x180002d7b  mov     rcx, [rcx+10h]
0x180002d7f  mov     edx, 11h
0x180002d84  mov     [rsp+58h+var_38], rdi
0x180002d89  call    WPP_SF_sq
0x180002d8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d95  test    rsi, rsi
0x180002d98  jz      short loc_180002E04
0x180002d9a  mov     qword ptr [rsi], 0
0x180002da1  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x180002da8  cmp     rax, [rbx]
0x180002dab  jnz     short loc_180002DBA
0x180002dad  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x180002db4  cmp     rax, [rbx+8]
0x180002db8  jz      short loc_180002DD3
0x180002dba  mov     rax, qword ptr cs:_GUID_29d809a4_4d61_4f18_9d00_b447e42a9831.Data1
0x180002dc1  cmp     rax, [rbx]
0x180002dc4  jnz     short loc_180002DF6
0x180002dc6  mov     rax, qword ptr cs:_GUID_29d809a4_4d61_4f18_9d00_b447e42a9831.Data4
0x180002dcd  cmp     rax, [rbx+8]
0x180002dd1  jnz     short loc_180002DF6
0x180002dd3  mov     rax, [rdi]
0x180002dd6  mov     rcx, rdi
0x180002dd9  xor     ebx, ebx
0x180002ddb  mov     rax, [rax+8]
0x180002ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002de4  mov     [rsi], rdi
0x180002de7  xor     eax, eax
0x180002de9  mov     rcx, cs:WPP_GLOBAL_Control
0x180002df0  cmp     byte ptr [rcx+19h], 4
0x180002df4  jmp     short loc_180002E0F
0x180002df6  mov     rcx, cs:WPP_GLOBAL_Control
0x180002dfd  mov     ebx, 80004002h
0x180002e02  jmp     short loc_180002E09
0x180002e04  mov     ebx, 80070057h
0x180002e09  xor     eax, eax
0x180002e0b  cmp     byte ptr [rcx+19h], 2
0x180002e0f  setnb   al
0x180002e12  cmp     rcx, rbp
0x180002e15  jz      short loc_180002E32
0x180002e17  test    eax, eax
0x180002e19  jz      short loc_180002E32
0x180002e1b  mov     rcx, [rcx+10h]
0x180002e1f  mov     edx, 12h
0x180002e24  mov     [rsp+58h+var_30], ebx
0x180002e28  mov     [rsp+58h+var_38], rdi
0x180002e2d  call    WPP_SF_sqd
0x180002e32  mov     eax, ebx
0x180002e34  add     rsp, 38h
0x180002e38  pop     rdi
0x180002e39  pop     rsi
0x180002e3a  pop     rbp
0x180002e3b  pop     rbx
0x180002e3c  retn
```
