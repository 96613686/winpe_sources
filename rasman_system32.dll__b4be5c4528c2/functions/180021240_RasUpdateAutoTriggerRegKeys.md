# RasUpdateAutoTriggerRegKeys

- ea: `0x180021240`
- end: `0x180021395`
- name: `RasUpdateAutoTriggerRegKeys`
- size: `341`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800030d0`
- `0x180021240`
- `0x180021b14`
- `0x180021c40`

## pseudocode

```c
__int64 __fastcall RasUpdateAutoTriggerRegKeys(
        __int64 a1,
        const char *a2,
        __int64 a3,
        int a4,
        int a5,
        const char *a6,
        int a7)
{
  const char *v11; // r11
  const char *v12; // rax
  unsigned int v13; // eax
  unsigned int v14; // ebx
  PVOID *v15; // rcx
  __int64 v17; // [rsp+20h] [rbp-78h]
  __int64 v18; // [rsp+28h] [rbp-70h]
  __int64 v19; // [rsp+38h] [rbp-60h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v11 = a6;
    v12 = a2;
    if ( !a6 )
      v11 = L"<NULL>";
    if ( !a2 )
      v12 = L"<NULL>";
    WPP_SF_SScccS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v12, a4 != 0, a5 != 0, a7 != 0, (__int64)v11);
  }
  LODWORD(v19) = a7;
  LODWORD(v18) = a5;
  LODWORD(v17) = a4;
  v13 = SubmitLocalRequest(0x91u, a1, a2, a3, v17, v18, a6, v19);
  v14 = v13;
  if ( !v13 )
    goto LABEL_14;
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v14;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 707, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v13);
LABEL_14:
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 0x40) != 0 && *((_BYTE *)v15 + 25) >= 6u )
    WPP_SF_d(v15[2], 708, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x180021240  push    rbx
0x180021242  push    rbp
0x180021243  push    rsi
0x180021244  push    rdi
0x180021245  push    r12
0x180021247  push    r13
0x180021249  push    r14
0x18002124b  push    r15
0x18002124d  sub     rsp, 58h
0x180021251  mov     ebp, r9d
0x180021254  mov     r12, r8
0x180021257  mov     rbx, rdx
0x18002125a  mov     rdi, rcx
0x18002125d  mov     rcx, cs:WPP_GLOBAL_Control
0x180021264  lea     r13, WPP_GLOBAL_Control
0x18002126b  mov     r14d, [rsp+98h+arg_30]
0x180021273  mov     rsi, [rsp+98h+arg_28]
0x18002127b  mov     r15d, [rsp+98h+arg_20]
0x180021283  cmp     rcx, r13
0x180021286  jz      short loc_1800212F5
0x180021288  test    byte ptr [rcx+1Ch], 40h
0x18002128c  jz      short loc_1800212F5
0x18002128e  cmp     byte ptr [rcx+19h], 6
0x180021292  jb      short loc_1800212F5
0x180021294  mov     rcx, [rcx+10h]; LoggerHandle
0x180021298  lea     r13, aNull_2; "<NULL>"
0x18002129f  test    rsi, rsi
0x1800212a2  mov     r11, rsi
0x1800212a5  mov     rax, rbx
0x1800212a8  cmovz   r11, r13
0x1800212ac  test    r14d, r14d
0x1800212af  mov     [rsp+98h+var_58], r11; __int64
0x1800212b4  setnz   r10b
0x1800212b8  test    r15d, r15d
0x1800212bb  mov     [rsp+98h+var_60], r10b; char
0x1800212c0  setnz   r8b
0x1800212c4  test    r9d, r9d
0x1800212c7  mov     [rsp+98h+var_68], r8b; char
0x1800212cc  mov     r9, rdi
0x1800212cf  setnz   dl
0x1800212d2  test    rbx, rbx
0x1800212d5  mov     [rsp+98h+var_70], dl; char
0x1800212d9  cmovz   rax, r13
0x1800212dd  test    rdi, rdi
0x1800212e0  mov     [rsp+98h+var_78], rax; __int64
0x1800212e5  cmovz   r9, r13
0x1800212e9  call    WPP_SF_SScccS
0x1800212ee  lea     r13, WPP_GLOBAL_Control
0x1800212f5  mov     dword ptr [rsp+98h+var_60], r14d
0x1800212fa  mov     ecx, 91h
0x1800212ff  mov     qword ptr [rsp+98h+var_68], rsi
0x180021304  mov     r9, r12
0x180021307  mov     dword ptr [rsp+98h+var_70], r15d
0x18002130c  mov     r8, rbx
0x18002130f  mov     rdx, rdi
0x180021312  mov     dword ptr [rsp+98h+var_78], ebp
0x180021316  call    SubmitLocalRequest
0x18002131b  mov     ebx, eax
0x18002131d  test    eax, eax
0x18002131f  jz      short loc_180021351
0x180021321  mov     rcx, cs:WPP_GLOBAL_Control
0x180021328  cmp     rcx, r13
0x18002132b  jz      short loc_180021381
0x18002132d  test    byte ptr [rcx+1Ch], 40h
0x180021331  jz      short loc_180021358
0x180021333  cmp     byte ptr [rcx+19h], 2
0x180021337  jb      short loc_180021358
0x180021339  mov     rcx, [rcx+10h]
0x18002133d  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180021344  mov     edx, 2C3h
0x180021349  mov     r9d, eax
0x18002134c  call    WPP_SF_d
0x180021351  mov     rcx, cs:WPP_GLOBAL_Control
0x180021358  cmp     rcx, r13
0x18002135b  jz      short loc_180021381
0x18002135d  test    byte ptr [rcx+1Ch], 40h
0x180021361  jz      short loc_180021381
0x180021363  cmp     byte ptr [rcx+19h], 6
0x180021367  jb      short loc_180021381
0x180021369  mov     rcx, [rcx+10h]
0x18002136d  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180021374  mov     edx, 2C4h
0x180021379  mov     r9d, ebx
0x18002137c  call    WPP_SF_d
0x180021381  mov     eax, ebx
0x180021383  add     rsp, 58h
0x180021387  pop     r15
0x180021389  pop     r14
0x18002138b  pop     r13
0x18002138d  pop     r12
0x18002138f  pop     rdi
0x180021390  pop     rsi
0x180021391  pop     rbp
0x180021392  pop     rbx
0x180021393  retn
```
