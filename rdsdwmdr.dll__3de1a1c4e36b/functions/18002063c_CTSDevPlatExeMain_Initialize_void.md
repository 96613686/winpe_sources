# CTSDevPlatExeMain::Initialize(void *)

- ea: `0x18002063c`
- end: `0x180020814`
- name: `?Initialize@CTSDevPlatExeMain@@QEAAJPEAX@Z`
- size: `472`
- prototype: `__int64 __fastcall(CTSDevPlatExeMain *__hidden this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001fd1c`

## callees

- `0x18001d114`
- `0x18001ef44`
- `0x18002063c`
- `0x18002164c`
- `0x180022490`
- `0x18002c010`

## string_xrefs

- `0x1800206e8`: `TSCreatePlatform failed`
- `0x180020798`: `ITSPlatform::CreateThread failed`
- `0x1800207df`: `ITSThread::BindThread failed`

## pseudocode

```c
__int64 __fastcall CTSDevPlatExeMain::Initialize(CTSDevPlatExeMain *this, void *a2)
{
  int v4; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v6; // edx
  const char *v7; // rcx
  _QWORD *v8; // rsi
  int v10; // [rsp+28h] [rbp-30h]

  v4 = TSPlatformStaticInit();
  if ( v4 >= 0 )
  {
    v8 = (_QWORD *)((char *)this + 8);
    *((_DWORD *)this + 4) = 1;
    v4 = TSCreatePlatform(a2, (char *)this + 8);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 24LL))(*v8);
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, CTSDevPlatExeMain *))(*(_QWORD *)*v8 + 56LL))(
               *v8,
               0,
               0,
               this);
        if ( v4 >= 0 )
        {
          v4 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 40LL))(*(_QWORD *)this);
          if ( v4 < 0
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v6 = 14;
            v7 = "ITSThread::BindThread failed";
            goto LABEL_26;
          }
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v6 = 13;
          v7 = "ITSPlatform::CreateThread failed";
          goto LABEL_26;
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v6 = 12;
        v7 = "ITSPlatform.Initialize failed";
        goto LABEL_26;
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 11;
      v7 = "TSCreatePlatform failed";
      goto LABEL_26;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 10;
    v7 = "TSPlatformStaticInit failed";
LABEL_26:
    v10 = v4;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      (unsigned int)WPP_2a05ac42153e3921f9cad13e82462e78_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v7,
      v10);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002063c  push    rbx
0x18002063e  push    rbp
0x18002063f  push    rsi
0x180020640  push    rdi
0x180020641  sub     rsp, 38h
0x180020645  mov     rbp, rdx
0x180020648  mov     rdi, rcx
0x18002064b  call    ?TSPlatformStaticInit@@YAJXZ; TSPlatformStaticInit(void)
0x180020650  mov     ebx, eax
0x180020652  test    eax, eax
0x180020654  jns     short loc_180020697
0x180020656  mov     rax, cs:WPP_GLOBAL_Control
0x18002065d  lea     rcx, WPP_GLOBAL_Control
0x180020664  cmp     rax, rcx
0x180020667  jz      loc_180020809
0x18002066d  test    byte ptr [rax+1Ch], 8
0x180020671  jz      loc_180020809
0x180020677  cmp     byte ptr [rax+19h], 2
0x18002067b  jb      loc_180020809
0x180020681  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180020686  mov     edx, 0Ah
0x18002068b  lea     rcx, aTsplatformstat_0; "TSPlatformStaticInit failed"
0x180020692  jmp     loc_1800207E6
0x180020697  lea     rsi, [rdi+8]
0x18002069b  mov     dword ptr [rdi+10h], 1
0x1800206a2  mov     rdx, rsi
0x1800206a5  mov     rcx, rbp
0x1800206a8  call    TSCreatePlatform
0x1800206ad  mov     ebx, eax
0x1800206af  test    eax, eax
0x1800206b1  jns     short loc_1800206F4
0x1800206b3  mov     rax, cs:WPP_GLOBAL_Control
0x1800206ba  lea     rcx, WPP_GLOBAL_Control
0x1800206c1  cmp     rax, rcx
0x1800206c4  jz      loc_180020809
0x1800206ca  test    byte ptr [rax+1Ch], 8
0x1800206ce  jz      loc_180020809
0x1800206d4  cmp     byte ptr [rax+19h], 2
0x1800206d8  jb      loc_180020809
0x1800206de  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800206e3  mov     edx, 0Bh
0x1800206e8  lea     rcx, aTscreateplatfo; "TSCreatePlatform failed"
0x1800206ef  jmp     loc_1800207E6
0x1800206f4  mov     rcx, [rsi]
0x1800206f7  mov     rax, [rcx]
0x1800206fa  mov     rax, [rax+18h]
0x1800206fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020703  mov     ebx, eax
0x180020705  test    eax, eax
0x180020707  jns     short loc_18002074A
0x180020709  mov     rax, cs:WPP_GLOBAL_Control
0x180020710  lea     rcx, WPP_GLOBAL_Control
0x180020717  cmp     rax, rcx
0x18002071a  jz      loc_180020809
0x180020720  test    byte ptr [rax+1Ch], 8
0x180020724  jz      loc_180020809
0x18002072a  cmp     byte ptr [rax+19h], 2
0x18002072e  jb      loc_180020809
0x180020734  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180020739  mov     edx, 0Ch
0x18002073e  lea     rcx, aItsplatformIni; "ITSPlatform.Initialize failed"
0x180020745  jmp     loc_1800207E6
0x18002074a  mov     rcx, [rsi]
0x18002074d  mov     r9, rdi
0x180020750  xor     r8d, r8d
0x180020753  xor     edx, edx
0x180020755  mov     rax, [rcx]
0x180020758  mov     rax, [rax+38h]
0x18002075c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020761  mov     ebx, eax
0x180020763  test    eax, eax
0x180020765  jns     short loc_1800207A1
0x180020767  mov     rax, cs:WPP_GLOBAL_Control
0x18002076e  lea     rcx, WPP_GLOBAL_Control
0x180020775  cmp     rax, rcx
0x180020778  jz      loc_180020809
0x18002077e  test    byte ptr [rax+1Ch], 8
0x180020782  jz      loc_180020809
0x180020788  cmp     byte ptr [rax+19h], 2
0x18002078c  jb      short loc_180020809
0x18002078e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180020793  mov     edx, 0Dh
0x180020798  lea     rcx, aItsplatformCre; "ITSPlatform::CreateThread failed"
0x18002079f  jmp     short loc_1800207E6
0x1800207a1  mov     rcx, [rdi]
0x1800207a4  mov     rax, [rcx]
0x1800207a7  mov     rax, [rax+28h]
0x1800207ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207b0  mov     ebx, eax
0x1800207b2  test    eax, eax
0x1800207b4  jns     short loc_180020809
0x1800207b6  mov     rax, cs:WPP_GLOBAL_Control
0x1800207bd  lea     rcx, WPP_GLOBAL_Control
0x1800207c4  cmp     rax, rcx
0x1800207c7  jz      short loc_180020809
0x1800207c9  test    byte ptr [rax+1Ch], 8
0x1800207cd  jz      short loc_180020809
0x1800207cf  cmp     byte ptr [rax+19h], 2
0x1800207d3  jb      short loc_180020809
0x1800207d5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800207da  mov     edx, 0Eh
0x1800207df  lea     rcx, aItsthreadBindt; "ITSThread::BindThread failed"
0x1800207e6  mov     [rsp+58h+var_30], ebx
0x1800207ea  lea     r8, WPP_2a05ac42153e3921f9cad13e82462e78_Traceguids
0x1800207f1  mov     [rsp+58h+var_38], rcx
0x1800207f6  mov     r9d, eax
0x1800207f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180020800  mov     rcx, [rcx+10h]
0x180020804  call    WPP_SF_DsD
0x180020809  mov     eax, ebx
0x18002080b  add     rsp, 38h
0x18002080f  pop     rdi
0x180020810  pop     rsi
0x180020811  pop     rbp
0x180020812  pop     rbx
0x180020813  retn
```
