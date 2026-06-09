# GmsapUpdateGMSAEntry(_tagGMsaListEntry *,_tagPasswordData *,int *)

- ea: `0x180005018`
- end: `0x1800052c8`
- name: `?GmsapUpdateGMSAEntry@@YAJPEAU_tagGMsaListEntry@@PEAU_tagPasswordData@@PEAH@Z`
- size: `688`
- prototype: `__int64 __fastcall(struct _tagGMsaListEntry *, struct _tagPasswordData *, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180002380`
- `0x180003e84`

## callees

- `0x180004318`
- `0x180005018`
- `0x180006280`
- `0x1800062b0`
- `0x180007bc1`
- `0x180007bcd`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000508a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800050ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000516d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000508a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800050ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000516d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005189`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800051c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800051ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000527a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005189`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800051c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800051ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000527a`

## pseudocode

```c
__int64 __fastcall GmsapUpdateGMSAEntry(FILETIME *a1, struct _tagPasswordData *a2, int *a3)
{
  DWORD dwLowDateTime; // r12d
  void *v5; // rbp
  int v8; // eax
  const void **v9; // rdi
  HLOCAL v10; // rax
  unsigned int v11; // ebx
  DWORD v12; // r14d
  HLOCAL v13; // rax
  void *v14; // r15
  HLOCAL v15; // r13
  DWORD *v16; // r14
  HLOCAL v17; // rax
  void *v18; // rcx
  __int64 v19; // rcx
  _BYTE *v20; // rax
  DWORD v22; // [rsp+60h] [rbp+8h]
  DWORD v23; // [rsp+68h] [rbp+10h]

  dwLowDateTime = 0;
  v5 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_70b8577d707437755865c965214ce19a_Traceguids);
  v8 = *((_DWORD *)a2 + 2);
  v9 = (const void **)&a1[8];
  *a3 = 0;
  if ( a1[9].dwHighDateTime != v8 || !*v9 )
    goto LABEL_9;
  dwLowDateTime = a1[9].dwLowDateTime;
  v10 = LocalAlloc(0x40u, dwLowDateTime);
  v5 = v10;
  if ( !v10 )
  {
    v11 = -1073741801;
    goto LABEL_28;
  }
  memcpy_0(v10, *v9, a1[9].dwLowDateTime);
  ((void (__fastcall *)(void *, _QWORD))xmmword_18000B5A0)(v5, a1[9].dwLowDateTime);
  if ( memcmp_0(v5, *(const void **)a2, a1[9].dwHighDateTime) )
LABEL_9:
    *a3 = 1;
  v12 = ((__int64 (__fastcall *)(_QWORD))xmmword_18000B590)(*((unsigned int *)a2 + 2));
  v23 = v12;
  v13 = LocalAlloc(0x40u, v12);
  v14 = v13;
  if ( !v13 )
  {
    v11 = -1073741801;
    goto LABEL_24;
  }
  v15 = 0;
  v22 = 0;
  memcpy_0(v13, *(const void **)a2, *((unsigned int *)a2 + 2));
  (*((void (__fastcall **)(void *, _QWORD))&xmmword_18000B590 + 1))(v14, v12);
  v16 = (DWORD *)((char *)a2 + 24);
  if ( !*((_DWORD *)a2 + 6) || !*((_QWORD *)a2 + 2) )
  {
LABEL_17:
    if ( *v9 )
    {
      LocalFree((HLOCAL)*v9);
      *v9 = 0;
      a1[9] = 0;
    }
    v18 = (void *)a1[10];
    if ( v18 )
    {
      LocalFree(v18);
      a1[10] = 0;
      a1[11] = 0;
    }
    *v9 = v14;
    a1[9].dwHighDateTime = *((_DWORD *)a2 + 2);
    a1[9].dwLowDateTime = v23;
    a1[10] = (FILETIME)v15;
    a1[11].dwHighDateTime = *v16;
    a1[11].dwLowDateTime = v22;
    a1[7] = *(FILETIME *)((char *)a2 + 28);
    if ( !GmsapIsSameFileTime(a1 + 5, (FILETIME *)((char *)a2 + 36)) )
    {
      a1[5] = *(FILETIME *)((char *)a2 + 36);
      a1[6] = *(FILETIME *)((char *)a2 + 44);
    }
    v11 = 0;
    goto LABEL_24;
  }
  v22 = ((__int64 (*)(void))xmmword_18000B590)();
  v17 = LocalAlloc(0x40u, v22);
  v15 = v17;
  if ( v17 )
  {
    memcpy_0(v17, *((const void **)a2 + 2), *v16);
    (*((void (__fastcall **)(HLOCAL, _QWORD))&xmmword_18000B590 + 1))(v15, v22);
    v16 = (DWORD *)((char *)a2 + 24);
    goto LABEL_17;
  }
  v11 = -1073741801;
  LocalFree(v14);
LABEL_24:
  if ( v5 )
  {
    v19 = dwLowDateTime;
    v20 = v5;
    if ( dwLowDateTime )
    {
      do
      {
        *v20++ = 0;
        --v19;
      }
      while ( v19 );
    }
    LocalFree(v5);
  }
LABEL_28:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_70b8577d707437755865c965214ce19a_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180005018  mov     [rsp+arg_10], rbx
0x18000501d  push    rbp
0x18000501e  push    rsi
0x18000501f  push    rdi
0x180005020  push    r12
0x180005022  push    r13
0x180005024  push    r14
0x180005026  push    r15
0x180005028  sub     rsp, 20h
0x18000502c  xor     r12d, r12d
0x18000502f  mov     r14, r8
0x180005032  xor     ebp, ebp
0x180005034  mov     rsi, rdx
0x180005037  mov     rbx, rcx
0x18000503a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005041  lea     r13, WPP_GLOBAL_Control
0x180005048  cmp     rcx, r13
0x18000504b  jz      short loc_180005066
0x18000504d  test    byte ptr [rcx+1Ch], 8
0x180005051  jz      short loc_180005066
0x180005053  mov     rcx, [rcx+10h]
0x180005057  lea     edx, [rbp+2Ah]
0x18000505a  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180005061  call    WPP_SF_
0x180005066  mov     eax, [rsi+8]
0x180005069  lea     rdi, [rbx+40h]
0x18000506d  mov     r15d, 40h ; '@'
0x180005073  mov     [r14], ebp
0x180005076  cmp     [rbx+4Ch], eax
0x180005079  jnz     short loc_1800050DC
0x18000507b  cmp     [rdi], rbp
0x18000507e  jz      short loc_1800050DC
0x180005080  mov     r12d, [rbx+48h]
0x180005084  mov     ecx, r15d; uFlags
0x180005087  mov     edx, r12d; uBytes
0x18000508a  call    cs:__imp_LocalAlloc
0x180005091  nop     dword ptr [rax+rax+00h]
0x180005096  mov     rbp, rax
0x180005099  test    rax, rax
0x18000509c  jnz     short loc_1800050A8
0x18000509e  mov     ebx, 0C0000017h
0x1800050a3  jmp     loc_180005286
0x1800050a8  mov     r8d, [rbx+48h]; Size
0x1800050ac  mov     rcx, rbp; void *
0x1800050af  mov     rdx, [rdi]; Src
0x1800050b2  call    memcpy_0
0x1800050b7  mov     edx, [rbx+48h]
0x1800050ba  mov     rcx, rbp
0x1800050bd  mov     rax, qword ptr cs:xmmword_18000B5A0
0x1800050c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050c9  mov     r8d, [rbx+4Ch]; Size
0x1800050cd  mov     rcx, rbp; Buf1
0x1800050d0  mov     rdx, [rsi]; Buf2
0x1800050d3  call    memcmp_0
0x1800050d8  test    eax, eax
0x1800050da  jz      short loc_1800050E3
0x1800050dc  mov     dword ptr [r14], 1
0x1800050e3  mov     ecx, [rsi+8]
0x1800050e6  mov     rax, qword ptr cs:xmmword_18000B590
0x1800050ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050f2  mov     r14d, eax
0x1800050f5  mov     ecx, r15d; uFlags
0x1800050f8  mov     edx, eax; uBytes
0x1800050fa  mov     [rsp+58h+arg_8], r14d
0x1800050ff  call    cs:__imp_LocalAlloc
0x180005106  nop     dword ptr [rax+rax+00h]
0x18000510b  mov     r15, rax
0x18000510e  test    rax, rax
0x180005111  jnz     short loc_18000511D
0x180005113  mov     ebx, 0C0000017h
0x180005118  jmp     loc_18000525B
0x18000511d  mov     r8d, [rsi+8]; Size
0x180005121  xor     r13d, r13d
0x180005124  mov     rdx, [rsi]; Src
0x180005127  mov     rcx, r15; void *
0x18000512a  mov     [rsp+58h+arg_0], r13d
0x18000512f  call    memcpy_0
0x180005134  mov     rax, qword ptr cs:xmmword_18000B590+8
0x18000513b  mov     edx, r14d
0x18000513e  mov     rcx, r15
0x180005141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005146  lea     r14, [rsi+18h]
0x18000514a  mov     ecx, [r14]
0x18000514d  test    ecx, ecx
0x18000514f  jz      short loc_1800051C0
0x180005151  cmp     [rsi+10h], r13
0x180005155  jz      short loc_1800051C0
0x180005157  mov     rax, qword ptr cs:xmmword_18000B590
0x18000515e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005163  mov     edx, eax; uBytes
0x180005165  lea     ecx, [r13+40h]; uFlags
0x180005169  mov     [rsp+58h+arg_0], eax
0x18000516d  call    cs:__imp_LocalAlloc
0x180005174  nop     dword ptr [rax+rax+00h]
0x180005179  mov     r13, rax
0x18000517c  test    rax, rax
0x18000517f  jnz     short loc_18000519A
0x180005181  mov     rcx, r15; hMem
0x180005184  mov     ebx, 0C0000017h
0x180005189  call    cs:__imp_LocalFree
0x180005190  nop     dword ptr [rax+rax+00h]
0x180005195  jmp     loc_180005254
0x18000519a  mov     r8d, [r14]; Size
0x18000519d  mov     rcx, r13; void *
0x1800051a0  mov     rdx, [rsi+10h]; Src
0x1800051a4  call    memcpy_0
0x1800051a9  mov     edx, [rsp+58h+arg_0]
0x1800051ad  mov     rcx, r13
0x1800051b0  mov     rax, qword ptr cs:xmmword_18000B590+8
0x1800051b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051bc  lea     r14, [rsi+18h]
0x1800051c0  mov     rcx, [rdi]; hMem
0x1800051c3  test    rcx, rcx
0x1800051c6  jz      short loc_1800051E3
0x1800051c8  call    cs:__imp_LocalFree
0x1800051cf  nop     dword ptr [rax+rax+00h]
0x1800051d4  mov     qword ptr [rdi], 0
0x1800051db  mov     qword ptr [rbx+48h], 0
0x1800051e3  mov     rcx, [rbx+50h]; hMem
0x1800051e7  test    rcx, rcx
0x1800051ea  jz      short loc_180005208
0x1800051ec  call    cs:__imp_LocalFree
0x1800051f3  nop     dword ptr [rax+rax+00h]
0x1800051f8  mov     qword ptr [rbx+50h], 0
0x180005200  mov     qword ptr [rbx+58h], 0
0x180005208  mov     [rdi], r15
0x18000520b  lea     rdx, [rsi+24h]; lpFileTime2
0x18000520f  mov     eax, [rsi+8]
0x180005212  lea     rcx, [rbx+28h]; lpFileTime1
0x180005216  mov     [rbx+4Ch], eax
0x180005219  mov     eax, [rsp+58h+arg_8]
0x18000521d  mov     [rbx+48h], eax
0x180005220  mov     [rbx+50h], r13
0x180005224  mov     eax, [r14]
0x180005227  mov     [rbx+5Ch], eax
0x18000522a  mov     eax, [rsp+58h+arg_0]
0x18000522e  mov     [rbx+58h], eax
0x180005231  mov     rax, [rsi+1Ch]
0x180005235  mov     [rbx+38h], rax
0x180005239  call    ?GmsapIsSameFileTime@@YAHPEBU_FILETIME@@0@Z; GmsapIsSameFileTime(_FILETIME const *,_FILETIME const *)
0x18000523e  test    eax, eax
0x180005240  jnz     short loc_180005252
0x180005242  mov     rax, [rsi+24h]
0x180005246  mov     [rbx+28h], rax
0x18000524a  mov     rax, [rsi+2Ch]
0x18000524e  mov     [rbx+30h], rax
0x180005252  xor     ebx, ebx
0x180005254  lea     r13, WPP_GLOBAL_Control
0x18000525b  test    rbp, rbp
0x18000525e  jz      short loc_180005286
0x180005260  mov     ecx, r12d
0x180005263  mov     rax, rbp
0x180005266  test    r12d, r12d
0x180005269  jz      short loc_180005277
0x18000526b  mov     byte ptr [rax], 0
0x18000526e  inc     rax
0x180005271  sub     rcx, 1
0x180005275  jnz     short loc_18000526B
0x180005277  mov     rcx, rbp; hMem
0x18000527a  call    cs:__imp_LocalFree
0x180005281  nop     dword ptr [rax+rax+00h]
0x180005286  mov     rcx, cs:WPP_GLOBAL_Control
0x18000528d  cmp     rcx, r13
0x180005290  jz      short loc_1800052B0
0x180005292  test    byte ptr [rcx+1Ch], 8
0x180005296  jz      short loc_1800052B0
0x180005298  mov     rcx, [rcx+10h]
0x18000529c  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x1800052a3  mov     edx, 2Bh ; '+'
0x1800052a8  mov     r9d, ebx
0x1800052ab  call    WPP_SF_D
0x1800052b0  mov     eax, ebx
0x1800052b2  mov     rbx, [rsp+58h+arg_10]
0x1800052b7  add     rsp, 20h
0x1800052bb  pop     r15
0x1800052bd  pop     r14
0x1800052bf  pop     r13
0x1800052c1  pop     r12
0x1800052c3  pop     rdi
0x1800052c4  pop     rsi
0x1800052c5  pop     rbp
0x1800052c6  retn
```
