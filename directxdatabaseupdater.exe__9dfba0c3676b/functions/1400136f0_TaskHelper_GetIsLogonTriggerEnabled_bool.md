# TaskHelper::GetIsLogonTriggerEnabled(bool &)

- ea: `0x1400136f0`
- end: `0x140013766`
- name: `?GetIsLogonTriggerEnabled@TaskHelper@@QEAAJAEA_N@Z`
- size: `118`
- prototype: `__int64 __fastcall(LPVOID *this, bool *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x1400100e0`
- `0x140010ce8`

## callees

- `0x14000a4bc`
- `0x1400136f0`
- `0x14001376c`
- `0x14001a010`

## string_xrefs

- `0x140013714`: `onecore\windows\directx\database\updater\exe\taskschedulerhelper.cpp`

## pseudocode

```c
__int64 __fastcall TaskHelper::GetIsLogonTriggerEnabled(LPVOID *this, bool *a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  LPVOID v7; // rcx
  int v8; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int16 v10; // [rsp+60h] [rbp+18h] BYREF

  v4 = TaskHelper::Init(this);
  if ( v4 < 0 )
  {
    v5 = 50;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\taskschedulerhelper.cpp",
      (const char *)(unsigned int)v4,
      v8);
    return (unsigned int)v4;
  }
  v7 = this[4];
  v10 = 0;
  v4 = (*(__int64 (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)v7 + 144LL))(v7, &v10);
  if ( v4 < 0 )
  {
    v5 = 53;
    goto LABEL_3;
  }
  *a2 = v10 != 0;
  return 0;
}

```

## disassembly

```asm
0x1400136f0  push    rbx
0x1400136f2  push    rbp
0x1400136f3  push    rsi
0x1400136f4  push    rdi
0x1400136f5  sub     rsp, 28h
0x1400136f9  mov     rsi, rdx
0x1400136fc  mov     rdi, rcx
0x1400136ff  call    ?Init@TaskHelper@@AEAAJXZ; TaskHelper::Init(void)
0x140013704  xor     ebp, ebp
0x140013706  mov     ebx, eax
0x140013708  test    eax, eax
0x14001370a  jns     short loc_140013727
0x14001370c  lea     edx, [rbp+32h]; void *
0x14001370f  mov     rcx, [rsp+48h]; this
0x140013714  lea     r8, aOnecoreWindows_0; "onecore\\windows\\directx\\database\\up"...
0x14001371b  mov     r9d, ebx; char *
0x14001371e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013723  mov     eax, ebx
0x140013725  jmp     short loc_14001375D
0x140013727  mov     rcx, [rdi+20h]
0x14001372b  lea     rdx, [rsp+48h+arg_10]
0x140013730  mov     [rsp+48h+arg_10], bp
0x140013735  mov     rax, [rcx]
0x140013738  mov     rax, [rax+90h]
0x14001373f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013744  mov     ebx, eax
0x140013746  test    eax, eax
0x140013748  jns     short loc_140013751
0x14001374a  mov     edx, 35h ; '5'
0x14001374f  jmp     short loc_14001370F
0x140013751  cmp     [rsp+48h+arg_10], bp
0x140013756  setnz   al
0x140013759  mov     [rsi], al
0x14001375b  xor     eax, eax
0x14001375d  add     rsp, 28h
0x140013761  pop     rdi
0x140013762  pop     rsi
0x140013763  pop     rbp
0x140013764  pop     rbx
0x140013765  retn
```
