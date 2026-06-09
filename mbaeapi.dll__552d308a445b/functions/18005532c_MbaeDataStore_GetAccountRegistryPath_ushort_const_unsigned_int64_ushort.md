# MbaeDataStore::_GetAccountRegistryPath(ushort const *,unsigned __int64,ushort *)

- ea: `0x18005532c`
- end: `0x180055442`
- name: `?_GetAccountRegistryPath@MbaeDataStore@@CAJPEBG_KPEAG@Z`
- size: `278`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180055154`

## callees

- `0x180009ec4`
- `0x180009f88`
- `0x18005532c`
- `0x180055448`
- `0x180055470`

## import_xrefs

- `MobileNetworking!GetPersistentRegPath` at `0x18005539e`
- `MobileNetworking!GetPersistentRegPath` at `0x18005539e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall MbaeDataStore::_GetAccountRegistryPath(const unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  int PersistentRegPath; // eax
  signed int v6; // ebx
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  v8 = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b4c09844385137d2bffbdf31c0c767e1_Traceguids);
  LODWORD(v8) = 260;
  if ( byte_18008884C )
    goto LABEL_9;
  PersistentRegPath = GetPersistentRegPath(0, L"MobileBroadbandAccounts\\Accounts", &v8, &qword_180088850);
  v6 = PersistentRegPath;
  if ( PersistentRegPath > 0 )
    v6 = (unsigned __int16)PersistentRegPath | 0x80070000;
  if ( v6 >= 0 )
  {
    byte_18008884C = 1;
LABEL_9:
    v6 = StringCchCopyW(a3, 0x104u, &qword_180088850);
    if ( v6 >= 0 )
    {
      if ( a1 )
      {
        v6 = StringCchCatW(a3, 0x104u, L"\\");
        if ( v6 >= 0 )
          v6 = StringCchCatW(a3, 0x104u, a1);
      }
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b4c09844385137d2bffbdf31c0c767e1_Traceguids, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005532c  mov     [rsp+arg_0], rbx
0x180055331  mov     [rsp+arg_10], rbp
0x180055336  mov     [rsp+arg_8], rdx
0x18005533b  push    rsi
0x18005533c  push    rdi
0x18005533d  push    r14
0x18005533f  sub     rsp, 20h
0x180055343  mov     rdi, r8
0x180055346  mov     rsi, rcx
0x180055349  mov     rcx, cs:WPP_GLOBAL_Control
0x180055350  lea     r14, WPP_GLOBAL_Control
0x180055357  cmp     rcx, r14
0x18005535a  jz      short loc_180055377
0x18005535c  test    byte ptr [rcx+1Ch], 10h
0x180055360  jz      short loc_180055377
0x180055362  mov     rcx, [rcx+10h]
0x180055366  lea     r8, WPP_b4c09844385137d2bffbdf31c0c767e1_Traceguids
0x18005536d  mov     edx, 0Ah
0x180055372  call    WPP_SF_
0x180055377  cmp     cs:byte_18008884C, 0
0x18005537e  mov     ebp, 104h
0x180055383  mov     dword ptr [rsp+38h+arg_8], ebp
0x180055387  jnz     short loc_1800553BE
0x180055389  lea     r9, qword_180088850
0x180055390  xor     ecx, ecx
0x180055392  lea     r8, [rsp+38h+arg_8]
0x180055397  lea     rdx, aMobilebroadban_0; "MobileBroadbandAccounts\\Accounts"
0x18005539e  call    cs:__imp_GetPersistentRegPath
0x1800553a4  mov     ebx, eax
0x1800553a6  test    eax, eax
0x1800553a8  jle     short loc_1800553B3
0x1800553aa  movzx   ebx, ax
0x1800553ad  or      ebx, 80070000h
0x1800553b3  test    ebx, ebx
0x1800553b5  js      short loc_180055403
0x1800553b7  mov     cs:byte_18008884C, 1
0x1800553be  lea     r8, qword_180088850; unsigned __int16 *
0x1800553c5  mov     rdx, rbp; unsigned __int64
0x1800553c8  mov     rcx, rdi; unsigned __int16 *
0x1800553cb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800553d0  mov     ebx, eax
0x1800553d2  test    eax, eax
0x1800553d4  js      short loc_180055403
0x1800553d6  test    rsi, rsi
0x1800553d9  jz      short loc_180055403
0x1800553db  lea     r8, asc_1800657D8; "\\"
0x1800553e2  mov     rdx, rbp; unsigned __int64
0x1800553e5  mov     rcx, rdi; unsigned __int16 *
0x1800553e8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800553ed  mov     ebx, eax
0x1800553ef  test    eax, eax
0x1800553f1  js      short loc_180055403
0x1800553f3  mov     r8, rsi; unsigned __int16 *
0x1800553f6  mov     rdx, rbp; unsigned __int64
0x1800553f9  mov     rcx, rdi; unsigned __int16 *
0x1800553fc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180055401  mov     ebx, eax
0x180055403  mov     rcx, cs:WPP_GLOBAL_Control
0x18005540a  cmp     rcx, r14
0x18005540d  jz      short loc_18005542D
0x18005540f  test    byte ptr [rcx+1Ch], 10h
0x180055413  jz      short loc_18005542D
0x180055415  mov     rcx, [rcx+10h]
0x180055419  lea     r8, WPP_b4c09844385137d2bffbdf31c0c767e1_Traceguids
0x180055420  mov     edx, 0Bh
0x180055425  mov     r9d, ebx
0x180055428  call    WPP_SF_d
0x18005542d  mov     rbp, [rsp+38h+arg_10]
0x180055432  mov     eax, ebx
0x180055434  mov     rbx, [rsp+38h+arg_0]
0x180055439  add     rsp, 20h
0x18005543d  pop     r14
0x18005543f  pop     rdi
0x180055440  pop     rsi
0x180055441  retn
```
