# CComponentData::_SaveAs(HWND__ *,CLogInfo *)

- ea: `0x1800087bc`
- end: `0x180008888`
- name: `?_SaveAs@CComponentData@@AEAAJPEAUHWND__@@PEAVCLogInfo@@@Z`
- size: `204`
- prototype: `int(CComponentData *__hidden this, HWND, struct CLogInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800056c0`

## callees

- `0x1800087bc`
- `0x1800172cc`
- `0x18001fd74`
- `0x180022292`
- `0x1800222d0`

## pseudocode

```c
__int64 __fastcall CComponentData::_SaveAs(CComponentData *this, HWND a2, struct CLogInfo *a3)
{
  __int64 result; // rax
  __int64 v7; // rax
  unsigned int v8; // r9d
  int v9[4]; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int16 v10; // [rsp+40h] [rbp-228h] BYREF
  _BYTE v11[526]; // [rsp+42h] [rbp-226h] BYREF

  v9[0] = 0;
  v10 = 0;
  memset_0(v11, 0, 0x208u);
  result = GetSaveFileAndType(a2, a3, (enum SAVE_TYPE *)v9, &v10, 0x105u);
  if ( (_DWORD)result == 1 )
    return 0;
  if ( (int)result >= 0 )
  {
    v7 = *((_QWORD *)this + 9);
    v8 = 8;
    if ( v7 )
    {
      if ( *(_DWORD *)(v7 + 1600) == 9 )
        v8 = 4;
    }
    return CLogInfo::SaveLogAs((__int64)a3, v9[0], &v10, v8);
  }
  return result;
}

```

## disassembly

```asm
0x1800087bc  mov     [rsp+arg_0], rbx
0x1800087c1  mov     [rsp+arg_18], rsi
0x1800087c6  push    rdi
0x1800087c7  sub     rsp, 260h
0x1800087ce  mov     rax, cs:__security_cookie
0x1800087d5  xor     rax, rsp
0x1800087d8  mov     [rsp+268h+var_18], rax
0x1800087e0  mov     rsi, r8
0x1800087e3  mov     [rsp+268h+var_238], 0
0x1800087eb  mov     rbx, rdx
0x1800087ee  mov     rdi, rcx
0x1800087f1  xor     eax, eax
0x1800087f3  lea     rcx, [rsp+268h+var_226]; void *
0x1800087f8  xor     edx, edx; Val
0x1800087fa  mov     [rsp+268h+var_228], ax
0x1800087ff  mov     r8d, 208h; Size
0x180008805  call    memset_0
0x18000880a  lea     r9, [rsp+268h+var_228]; unsigned __int16 *
0x18000880f  mov     [rsp+268h+var_248], 105h; unsigned int
0x180008817  lea     r8, [rsp+268h+var_238]; enum SAVE_TYPE *
0x18000881c  mov     rdx, rsi; struct CLogInfo *
0x18000881f  mov     rcx, rbx; HWND
0x180008822  call    ?GetSaveFileAndType@@YAJPEAUHWND__@@PEAVCLogInfo@@PEAW4SAVE_TYPE@@PEAGK@Z; GetSaveFileAndType(HWND__ *,CLogInfo *,SAVE_TYPE *,ushort *,ulong)
0x180008827  cmp     eax, 1
0x18000882a  jnz     short loc_180008830
0x18000882c  xor     eax, eax
0x18000882e  jmp     short loc_180008863
0x180008830  test    eax, eax
0x180008832  js      short loc_180008863
0x180008834  mov     rax, [rdi+48h]
0x180008838  mov     r9d, 8
0x18000883e  test    rax, rax
0x180008841  jz      short loc_180008852
0x180008843  cmp     dword ptr [rax+640h], 9
0x18000884a  lea     ecx, [r9-4]
0x18000884e  cmovz   r9d, ecx
0x180008852  mov     edx, [rsp+268h+var_238]
0x180008856  lea     r8, [rsp+268h+var_228]
0x18000885b  mov     rcx, rsi
0x18000885e  call    ?SaveLogAs@CLogInfo@@QEAAJW4SAVE_TYPE@@PEBGW4DIRECTION@@@Z; CLogInfo::SaveLogAs(SAVE_TYPE,ushort const *,DIRECTION)
0x180008863  mov     rcx, [rsp+268h+var_18]
0x18000886b  xor     rcx, rsp; StackCookie
0x18000886e  call    __security_check_cookie
0x180008873  lea     r11, [rsp+268h+var_8]
0x18000887b  mov     rbx, [r11+10h]
0x18000887f  mov     rsi, [r11+28h]
0x180008883  mov     rsp, r11
0x180008886  pop     rdi
0x180008887  retn
```
