# CMsftDiscInformation::Init(IDiscRecorder2Ex *)

- ea: `0x180017f58`
- end: `0x180018149`
- name: `?Init@CMsftDiscInformation@@QEAAJPEAUIDiscRecorder2Ex@@@Z`
- size: `497`
- prototype: `__int64 __fastcall(CMsftDiscInformation *__hidden this, struct IDiscRecorder2Ex *)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800134e8`
- `0x180014288`
- `0x1800171d8`

## callees

- `0x180007bd4`
- `0x180017f58`
- `0x1800184c2`
- `0x180019010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180018130`
- `ole32!CoTaskMemFree` at `0x180018130`
- `KERNEL32!LocalFree` at `0x1800180e1`
- `KERNEL32!LocalFree` at `0x1800180e1`
- `KERNEL32!Sleep` at `0x180017fe5`
- `KERNEL32!Sleep` at `0x180017fe5`
- `KERNEL32!LocalAlloc` at `0x1800180b6`
- `KERNEL32!LocalAlloc` at `0x1800180b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMsftDiscInformation::Init(CMsftDiscInformation *this, struct IDiscRecorder2Ex *a2)
{
  int v4; // ebx
  unsigned int i; // edi
  unsigned int v6; // eax
  size_t v7; // rdi
  __int64 v8; // r9
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  void *v11; // rbp
  void *v12; // rcx
  HLOCAL v13; // rax
  HLOCAL v14; // r14
  int v16; // [rsp+60h] [rbp+18h] BYREF
  void *Src; // [rsp+68h] [rbp+20h] BYREF

  v4 = 0;
  Src = 0;
  v16 = 0;
  for ( i = 0; i < 0xA; ++i )
  {
    v6 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, void **, int *))a2->lpVtbl->GetDiscInformation)(
           a2,
           &Src,
           &v16);
    v4 = v6;
    if ( ((v6 + 1062600187) & 0xFFFFFFFD) != 0 )
      break;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_7fbbfb794ace3f4195f7fb7939ddc37a_Traceguids, v6);
    }
    Sleep(0x2710u);
  }
  if ( v4 >= 0 )
  {
    if ( Src
      && (v7 = v16, v16 >= 2)
      && (unsigned __int64)v16 >= 9
      && v16 == (*((unsigned __int8 *)Src + 1) | (*(unsigned __int8 *)Src << 8)) + 2 )
    {
      v11 = Src;
      if ( Src && v16 > 8 && v16 == (*((unsigned __int8 *)Src + 1) | (*(unsigned __int8 *)Src << 8)) + 2 )
      {
        v4 = 0;
        v12 = *(void **)this;
        if ( *(_QWORD *)this && *((_DWORD *)this + 3) >= (unsigned int)v16 )
        {
          *((_DWORD *)this + 2) = v16;
          memcpy_0(v12, v11, v7);
        }
        else
        {
          v13 = LocalAlloc(0x40u, v16);
          v14 = v13;
          if ( v13 )
          {
            memcpy_0(v13, v11, v7);
            if ( *(_QWORD *)this )
              LocalFree(*(HLOCAL *)this);
            *(_QWORD *)this = v14;
            *((_DWORD *)this + 2) = v7;
            *((_DWORD *)this + 3) = v7;
          }
          else
          {
            v4 = -2147024882;
          }
        }
      }
      else
      {
        v4 = -1062599937;
      }
      if ( v4 < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v10 = 12;
          v8 = (unsigned int)v4;
          goto LABEL_35;
        }
      }
    }
    else
    {
      v4 = -1062599937;
      v8 = 3232367359LL;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v10 = 11;
LABEL_35:
        WPP_SF_d(v9[2], v10, WPP_7fbbfb794ace3f4195f7fb7939ddc37a_Traceguids, v8);
      }
    }
  }
  CoTaskMemFree(Src);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180017f58  mov     [rsp+arg_0], rbx
0x180017f5d  push    rbp
0x180017f5e  push    rsi
0x180017f5f  push    rdi
0x180017f60  push    r14
0x180017f62  push    r15
0x180017f64  sub     rsp, 20h
0x180017f68  mov     r14, rdx
0x180017f6b  mov     rsi, rcx
0x180017f6e  xor     ebx, ebx
0x180017f70  mov     [rsp+48h+Src], rbx
0x180017f75  mov     [rsp+48h+arg_10], ebx
0x180017f79  xor     edi, edi
0x180017f7b  lea     r15, WPP_GLOBAL_Control
0x180017f82  cmp     edi, 0Ah
0x180017f85  jnb     short loc_180017FEF
0x180017f87  mov     rax, [r14]
0x180017f8a  lea     r8, [rsp+48h+arg_10]
0x180017f8f  lea     rdx, [rsp+48h+Src]
0x180017f94  mov     rcx, r14
0x180017f97  mov     rax, [rax+50h]
0x180017f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fa0  mov     ebx, eax
0x180017fa2  lea     ecx, [rax+3F55FDFBh]
0x180017fa8  test    ecx, 0FFFFFFFDh
0x180017fae  jnz     short loc_180017FEF
0x180017fb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180017fb7  cmp     rcx, r15
0x180017fba  jz      short loc_180017FE0
0x180017fbc  test    byte ptr [rcx+1Ch], 4
0x180017fc0  jz      short loc_180017FE0
0x180017fc2  cmp     byte ptr [rcx+19h], 3
0x180017fc6  jb      short loc_180017FE0
0x180017fc8  mov     edx, 0Ah
0x180017fcd  mov     r9d, eax
0x180017fd0  lea     r8, WPP_7fbbfb794ace3f4195f7fb7939ddc37a_Traceguids
0x180017fd7  mov     rcx, [rcx+10h]
0x180017fdb  call    WPP_SF_d
0x180017fe0  mov     ecx, 2710h; dwMilliseconds
0x180017fe5  call    cs:__imp_Sleep
0x180017feb  inc     edi
0x180017fed  jmp     short loc_180017F82
0x180017fef  test    ebx, ebx
0x180017ff1  js      loc_18001812B
0x180017ff7  cmp     [rsp+48h+Src], 0
0x180017ffd  jz      short loc_180018027
0x180017fff  movsxd  rdi, [rsp+48h+arg_10]
0x180018004  cmp     edi, 2
0x180018007  jl      short loc_180018027
0x180018009  cmp     rdi, 9
0x18001800d  jb      short loc_180018027
0x18001800f  mov     rax, [rsp+48h+Src]
0x180018014  movzx   ecx, byte ptr [rax]
0x180018017  shl     ecx, 8
0x18001801a  movzx   eax, byte ptr [rax+1]
0x18001801e  or      ecx, eax
0x180018020  add     ecx, 2
0x180018023  cmp     edi, ecx
0x180018025  jz      short loc_18001805D
0x180018027  mov     ebx, 0C0AA02FFh
0x18001802c  mov     r9d, ebx
0x18001802f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018036  cmp     rcx, r15
0x180018039  jz      loc_18001812B
0x18001803f  test    byte ptr [rcx+1Ch], 4
0x180018043  jz      loc_18001812B
0x180018049  cmp     byte ptr [rcx+19h], 3
0x18001804d  jb      loc_18001812B
0x180018053  mov     edx, 0Bh
0x180018058  jmp     loc_18001811B
0x18001805d  mov     rbp, [rsp+48h+Src]
0x180018062  test    rbp, rbp
0x180018065  jnz     short loc_180018071
0x180018067  mov     ebx, 0C0AA02FFh
0x18001806c  jmp     loc_1800180F7
0x180018071  cmp     edi, 2
0x180018074  jl      short loc_180018067
0x180018076  cmp     edi, 9
0x180018079  jb      short loc_180018067
0x18001807b  movzx   ecx, byte ptr [rbp+0]
0x18001807f  shl     ecx, 8
0x180018082  movzx   eax, byte ptr [rbp+1]
0x180018086  or      ecx, eax
0x180018088  add     ecx, 2
0x18001808b  cmp     edi, ecx
0x18001808d  jnz     short loc_180018067
0x18001808f  xor     ebx, ebx
0x180018091  mov     rcx, [rsi]; void *
0x180018094  test    rcx, rcx
0x180018097  jz      short loc_1800180AE
0x180018099  cmp     [rsi+0Ch], edi
0x18001809c  jb      short loc_1800180AE
0x18001809e  mov     [rsi+8], edi
0x1800180a1  mov     r8, rdi; Size
0x1800180a4  mov     rdx, rbp; Src
0x1800180a7  call    memcpy_0
0x1800180ac  jmp     short loc_1800180F7
0x1800180ae  mov     rdx, rdi; uBytes
0x1800180b1  mov     ecx, 40h ; '@'; uFlags
0x1800180b6  call    cs:__imp_LocalAlloc
0x1800180bc  mov     r14, rax
0x1800180bf  test    rax, rax
0x1800180c2  jnz     short loc_1800180CB
0x1800180c4  mov     ebx, 8007000Eh
0x1800180c9  jmp     short loc_1800180F0
0x1800180cb  mov     r8, rdi; Size
0x1800180ce  mov     rdx, rbp; Src
0x1800180d1  mov     rcx, r14; void *
0x1800180d4  call    memcpy_0
0x1800180d9  mov     rcx, [rsi]; hMem
0x1800180dc  test    rcx, rcx
0x1800180df  jz      short loc_1800180E7
0x1800180e1  call    cs:__imp_LocalFree
0x1800180e7  mov     [rsi], r14
0x1800180ea  mov     [rsi+8], edi
0x1800180ed  mov     [rsi+0Ch], edi
0x1800180f0  lea     r15, WPP_GLOBAL_Control
0x1800180f7  test    ebx, ebx
0x1800180f9  jns     short loc_18001812B
0x1800180fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180018102  cmp     rcx, r15
0x180018105  jz      short loc_18001812B
0x180018107  test    byte ptr [rcx+1Ch], 4
0x18001810b  jz      short loc_18001812B
0x18001810d  cmp     byte ptr [rcx+19h], 3
0x180018111  jb      short loc_18001812B
0x180018113  mov     edx, 0Ch
0x180018118  mov     r9d, ebx
0x18001811b  lea     r8, WPP_7fbbfb794ace3f4195f7fb7939ddc37a_Traceguids
0x180018122  mov     rcx, [rcx+10h]
0x180018126  call    WPP_SF_d
0x18001812b  mov     rcx, [rsp+48h+Src]; pv
0x180018130  call    cs:__imp_CoTaskMemFree
0x180018136  mov     eax, ebx
0x180018138  mov     rbx, [rsp+48h+arg_0]
0x18001813d  add     rsp, 20h
0x180018141  pop     r15
0x180018143  pop     r14
0x180018145  pop     rdi
0x180018146  pop     rsi
0x180018147  pop     rbp
0x180018148  retn
```
