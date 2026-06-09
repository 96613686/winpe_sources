# RasPortOpenEx

- ea: `0x18001c280`
- end: `0x18001c48b`
- name: `RasPortOpenEx`
- size: `523`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x180001c40`
- `0x1800030d0`
- `0x18001c280`
- `0x1800205f0`
- `0x180021ae4`
- `0x180021b14`
- `0x180021f24`
- `0x180025bf8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c417`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c417`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c394`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c394`

## pseudocode

```c
__int64 __fastcall RasPortOpenEx(__int64 a1, unsigned int a2, _QWORD *a3, __int64 a4, __int64 a5)
{
  unsigned int v9; // eax
  unsigned int v10; // edi
  int v11; // eax
  __int64 v12; // r9
  int v13; // ebx
  PVOID *v14; // rcx
  HLOCAL v15; // rax
  void *v16; // rbx
  unsigned int UserSid; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  v9 = SubmitLocalRequest(0x61u, a1, a2, a4, 1, a5, a3);
  v10 = v9;
  if ( v9
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
  }
  v11 = IsRasmanProcess();
  v13 = v11;
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    LOBYTE(v12) = v11 != 0;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v12);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 )
    goto LABEL_35;
  if ( v13 && !NtCurrentTeb()->IsImpersonating )
    goto LABEL_34;
  v15 = LocalAlloc(0x40u, 0x1388u);
  v16 = v15;
  if ( v15 )
  {
    UserSid = GetUserSid((__int64)v15);
    if ( UserSid )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_29;
      }
      v19 = 98;
    }
    else
    {
      UserSid = RasSetPortUserData(*a3, 8, v16, 5000);
      if ( !UserSid )
        goto LABEL_29;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_29;
      }
      v19 = 97;
    }
    WPP_SF_d(v18[2], v19, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, UserSid);
LABEL_29:
    LocalFree(v16);
LABEL_34:
    v14 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_35;
  }
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v10;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
    goto LABEL_34;
  }
LABEL_35:
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 0x40) != 0 && *((_BYTE *)v14 + 25) >= 6u )
    WPP_SF_d(v14[2], 100, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18001c280  push    rbx
0x18001c282  push    rsi
0x18001c283  push    rdi
0x18001c284  push    r12
0x18001c286  push    r14
0x18001c288  push    r15
0x18001c28a  sub     rsp, 48h
0x18001c28e  mov     rbx, r9
0x18001c291  mov     r14, r8
0x18001c294  mov     edi, edx
0x18001c296  mov     rsi, rcx
0x18001c299  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c2a0  lea     r15, WPP_GLOBAL_Control
0x18001c2a7  lea     r12, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c2ae  cmp     rcx, r15
0x18001c2b1  jz      short loc_18001C2D0
0x18001c2b3  test    byte ptr [rcx+1Ch], 40h
0x18001c2b7  jz      short loc_18001C2D0
0x18001c2b9  cmp     byte ptr [rcx+19h], 6
0x18001c2bd  jb      short loc_18001C2D0
0x18001c2bf  mov     rcx, [rcx+10h]
0x18001c2c3  mov     edx, 5Eh ; '^'
0x18001c2c8  mov     r8, r12
0x18001c2cb  call    WPP_SF_
0x18001c2d0  mov     rax, [rsp+78h+arg_20]
0x18001c2d8  mov     ecx, 61h ; 'a'
0x18001c2dd  mov     [rsp+78h+var_48], r14
0x18001c2e2  mov     r9, rbx
0x18001c2e5  mov     [rsp+78h+var_50], rax
0x18001c2ea  mov     r8d, edi
0x18001c2ed  mov     rdx, rsi
0x18001c2f0  mov     [rsp+78h+var_58], 1
0x18001c2f8  call    SubmitLocalRequest
0x18001c2fd  mov     edi, eax
0x18001c2ff  test    eax, eax
0x18001c301  jz      short loc_18001C32F
0x18001c303  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c30a  cmp     rcx, r15
0x18001c30d  jz      short loc_18001C32F
0x18001c30f  test    byte ptr [rcx+1Ch], 40h
0x18001c313  jz      short loc_18001C32F
0x18001c315  cmp     byte ptr [rcx+19h], 2
0x18001c319  jb      short loc_18001C32F
0x18001c31b  mov     rcx, [rcx+10h]
0x18001c31f  mov     edx, 5Fh ; '_'
0x18001c324  mov     r9d, eax
0x18001c327  mov     r8, r12
0x18001c32a  call    WPP_SF_d
0x18001c32f  call    IsRasmanProcess
0x18001c334  mov     ebx, eax
0x18001c336  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c33d  cmp     rcx, r15
0x18001c340  jz      short loc_18001C36C
0x18001c342  test    byte ptr [rcx+1Ch], 40h
0x18001c346  jz      short loc_18001C36C
0x18001c348  cmp     byte ptr [rcx+19h], 5
0x18001c34c  jb      short loc_18001C36C
0x18001c34e  mov     rcx, [rcx+10h]
0x18001c352  test    eax, eax
0x18001c354  mov     edx, 60h ; '`'
0x18001c359  mov     r8, r12
0x18001c35c  setnz   r9b
0x18001c360  call    WPP_SF_c
0x18001c365  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c36c  test    edi, edi
0x18001c36e  jnz     loc_18001C455
0x18001c374  test    ebx, ebx
0x18001c376  jz      short loc_18001C388
0x18001c378  mov     eax, gs:179Ch
0x18001c380  test    eax, eax
0x18001c382  jz      loc_18001C44E
0x18001c388  mov     esi, 1388h
0x18001c38d  mov     ecx, 40h ; '@'; uFlags
0x18001c392  mov     edx, esi; uBytes
0x18001c394  call    cs:__imp_LocalAlloc
0x18001c39b  nop     dword ptr [rax+rax+00h]
0x18001c3a0  mov     rbx, rax
0x18001c3a3  test    rax, rax
0x18001c3a6  jz      short loc_18001C425
0x18001c3a8  mov     rcx, rax
0x18001c3ab  call    GetUserSid
0x18001c3b0  test    eax, eax
0x18001c3b2  jnz     short loc_18001C3E8
0x18001c3b4  mov     rcx, [r14]
0x18001c3b7  lea     edx, [rax+8]
0x18001c3ba  mov     r9d, esi
0x18001c3bd  mov     r8, rbx
0x18001c3c0  call    RasSetPortUserData
0x18001c3c5  test    eax, eax
0x18001c3c7  jz      short loc_18001C414
0x18001c3c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c3d0  cmp     rcx, r15
0x18001c3d3  jz      short loc_18001C414
0x18001c3d5  test    byte ptr [rcx+1Ch], 40h
0x18001c3d9  jz      short loc_18001C414
0x18001c3db  cmp     byte ptr [rcx+19h], 2
0x18001c3df  jb      short loc_18001C414
0x18001c3e1  mov     edx, 61h ; 'a'
0x18001c3e6  jmp     short loc_18001C405
0x18001c3e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c3ef  cmp     rcx, r15
0x18001c3f2  jz      short loc_18001C414
0x18001c3f4  test    byte ptr [rcx+1Ch], 40h
0x18001c3f8  jz      short loc_18001C414
0x18001c3fa  cmp     byte ptr [rcx+19h], 2
0x18001c3fe  jb      short loc_18001C414
0x18001c400  mov     edx, 62h ; 'b'
0x18001c405  mov     rcx, [rcx+10h]
0x18001c409  mov     r9d, eax
0x18001c40c  mov     r8, r12
0x18001c40f  call    WPP_SF_d
0x18001c414  mov     rcx, rbx; hMem
0x18001c417  call    cs:__imp_LocalFree
0x18001c41e  nop     dword ptr [rax+rax+00h]
0x18001c423  jmp     short loc_18001C44E
0x18001c425  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c42c  cmp     rcx, r15
0x18001c42f  jz      short loc_18001C47A
0x18001c431  test    byte ptr [rcx+1Ch], 40h
0x18001c435  jz      short loc_18001C455
0x18001c437  cmp     byte ptr [rcx+19h], 3
0x18001c43b  jb      short loc_18001C455
0x18001c43d  mov     rcx, [rcx+10h]
0x18001c441  mov     edx, 63h ; 'c'
0x18001c446  mov     r8, r12
0x18001c449  call    WPP_SF_
0x18001c44e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c455  cmp     rcx, r15
0x18001c458  jz      short loc_18001C47A
0x18001c45a  test    byte ptr [rcx+1Ch], 40h
0x18001c45e  jz      short loc_18001C47A
0x18001c460  cmp     byte ptr [rcx+19h], 6
0x18001c464  jb      short loc_18001C47A
0x18001c466  mov     rcx, [rcx+10h]
0x18001c46a  mov     edx, 64h ; 'd'
0x18001c46f  mov     r9d, edi
0x18001c472  mov     r8, r12
0x18001c475  call    WPP_SF_d
0x18001c47a  mov     eax, edi
0x18001c47c  add     rsp, 48h
0x18001c480  pop     r15
0x18001c482  pop     r14
0x18001c484  pop     r12
0x18001c486  pop     rdi
0x18001c487  pop     rsi
0x18001c488  pop     rbx
0x18001c489  retn
```
