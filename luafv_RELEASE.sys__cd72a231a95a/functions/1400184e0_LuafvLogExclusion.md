# LuafvLogExclusion

- ea: `0x1400184e0`
- end: `0x1400185b6`
- name: `LuafvLogExclusion`
- size: `214`
- prototype: `__int64 __fastcall(__int64, int, __int64, int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140018f20`
- `0x140025300`
- `0x140025820`

## callees

- `0x140005bb0`
- `0x1400184e0`
- `0x14001892c`

## pseudocode

```c
__int64 __fastcall LuafvLogExclusion(__int64 a1, int a2, __int64 a3, int a4)
{
  __int64 v4; // rax
  int v5; // r10d
  _DWORD *v6; // rcx
  _DWORD *v7; // rax
  _DWORD v9[4]; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v11; // [rsp+C0h] [rbp-40h]
  __int64 v12; // [rsp+C8h] [rbp-38h]
  _DWORD *v13; // [rsp+D0h] [rbp-30h]
  __int64 v14; // [rsp+D8h] [rbp-28h]
  __int64 v15; // [rsp+E0h] [rbp-20h]
  __int64 v16; // [rsp+E8h] [rbp-18h]
  int *v17; // [rsp+F0h] [rbp-10h]
  __int64 v18; // [rsp+F8h] [rbp-8h]
  int v19; // [rsp+138h] [rbp+38h] BYREF

  v19 = a4;
  v18 = 4;
  v17 = &v19;
  v4 = *(_QWORD *)(a1 + 16);
  v5 = a1;
  v9[0] = 0;
  v16 = 1;
  v15 = v4 + 4;
  if ( a3 )
  {
    v6 = (_DWORD *)(a3 + 40);
    v7 = (_DWORD *)(a3 + 44);
  }
  else
  {
    if ( *(_BYTE *)(v4 + 4) )
    {
      v11 = v9;
      v7 = v9;
      goto LABEL_4;
    }
    v6 = (_DWORD *)(v4 + 32);
    v7 = (_DWORD *)(*(_QWORD *)(v4 + 24) + 16LL);
  }
  v11 = v6;
LABEL_4:
  v13 = v7;
  v14 = 4;
  v12 = 4;
  return LuafvLogFileEvent(v5, a2, 0, 0, &LuafvExclusionEvent, &v10, 0xBu);
}

```

## disassembly

```asm
0x1400184e0  mov     [rsp-8+arg_18], r9d
0x1400184e5  push    rbp
0x1400184e6  lea     rbp, [rsp-10h]
0x1400184eb  sub     rsp, 110h
0x1400184f2  mov     rax, cs:__security_cookie
0x1400184f9  xor     rax, rsp
0x1400184fc  mov     [rbp+10h+var_10], rax
0x140018500  lea     rax, [rbp+10h+arg_18]
0x140018504  mov     [rbp+10h+var_18], 4
0x14001850c  xor     r9d, r9d; int
0x14001850f  mov     [rbp+10h+var_20], rax
0x140018513  mov     rax, [rcx+10h]
0x140018517  mov     r10, rcx
0x14001851a  mov     [rsp+110h+var_D0], r9d
0x14001851f  mov     [rbp+10h+var_28], 1
0x140018527  lea     rcx, [rax+4]
0x14001852b  mov     [rbp+10h+var_30], rcx
0x14001852f  test    r8, r8
0x140018532  jz      short loc_140018593
0x140018534  lea     rcx, [r8+28h]
0x140018538  lea     rax, [r8+2Ch]
0x14001853c  mov     [rbp+10h+var_50], rcx
0x140018540  mov     [rbp+10h+var_40], rax
0x140018544  xor     r8d, r8d; int
0x140018547  lea     rax, [rsp+110h+var_C0]
0x14001854c  mov     [rsp+110h+UserDataCount], 0Bh; UserDataCount
0x140018554  mov     [rsp+110h+var_E8], rax; PEVENT_DATA_DESCRIPTOR
0x140018559  mov     rcx, r10; int
0x14001855c  lea     rax, LuafvExclusionEvent
0x140018563  mov     [rbp+10h+var_38], 4
0x14001856b  mov     [rsp+110h+EventDescriptor], rax; EventDescriptor
0x140018570  mov     [rbp+10h+var_48], 4
0x140018578  call    LuafvLogFileEvent
0x14001857d  mov     rcx, [rbp+10h+var_10]
0x140018581  xor     rcx, rsp; StackCookie
0x140018584  call    __security_check_cookie
0x140018589  add     rsp, 110h
0x140018590  pop     rbp
0x140018591  retn
0x140018593  cmp     [rcx], r9b
0x140018596  jz      short loc_1400185A8
0x140018598  lea     rax, [rsp+110h+var_D0]
0x14001859d  mov     [rbp+10h+var_50], rax
0x1400185a1  lea     rax, [rsp+110h+var_D0]
0x1400185a6  jmp     short loc_140018540
0x1400185a8  lea     rcx, [rax+20h]
0x1400185ac  mov     rax, [rax+18h]
0x1400185b0  add     rax, 10h
0x1400185b4  jmp     short loc_14001853C
```
