# FveBcdUtil::GetAssociatedOs(void *,_GUID *)

- ea: `0x1800da860`
- end: `0x1800daa5f`
- name: `?GetAssociatedOs@FveBcdUtil@@SAJPEAXPEAU_GUID@@@Z`
- size: `511`
- prototype: `__int64 __fastcall(void *, struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800daa68`

## callees

- `0x1800090c0`
- `0x180018b10`
- `0x180047570`
- `0x1800da860`
- `0x1800dabb8`
- `0x1800dad64`
- `0x1800dadec`
- `0x18011f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800daa29`
- `msvcrt!??3@YAXPEAX@Z` at `0x180128ab5`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800daa29`
- `msvcrt!??3@YAXPEAX@Z` at `0x180128ab5`
- `bcd!BcdCloseObject` at `0x1800daa13`
- `bcd!BcdCloseObject` at `0x180128a9f`
- `bcd!BcdCloseObject` at `0x1800daa13`
- `bcd!BcdCloseObject` at `0x180128a9f`
- `bcd!BcdOpenObject` at `0x1800da912`
- `bcd!BcdOpenObject` at `0x1800da912`

## pseudocode

```c
__int64 __fastcall FveBcdUtil::GetAssociatedOs(void *a1, struct _GUID *a2)
{
  unsigned __int8 v4; // r14
  int DoesRegKeyExist; // ebx
  int v6; // eax
  int BcdElementData; // eax
  unsigned int v8; // esi
  unsigned int i; // edi
  struct _GUID *v10; // r12
  int IsAssociatedOS; // eax
  unsigned __int8 v13[4]; // [rsp+20h] [rbp-68h] BYREF
  int v14; // [rsp+24h] [rbp-64h]
  int v15; // [rsp+28h] [rbp-60h] BYREF
  unsigned int v16; // [rsp+2Ch] [rbp-5Ch] BYREF
  void *v17; // [rsp+30h] [rbp-58h] BYREF
  void *v18; // [rsp+38h] [rbp-50h] BYREF
  unsigned int v19; // [rsp+40h] [rbp-48h]
  struct _GUID v20; // [rsp+48h] [rbp-40h] BYREF

  v20 = 0;
  v17 = 0;
  v18 = 0;
  v16 = 0;
  v4 = 0;
  v13[0] = 0;
  v15 = 0;
  DoesRegKeyExist = NgscbpDoesRegKeyExist((__int64)a1, (__int64)a2, &v15);
  v14 = DoesRegKeyExist;
  if ( DoesRegKeyExist >= 0 )
  {
    if ( !v15 )
    {
LABEL_3:
      DoesRegKeyExist = -2147024809;
      v14 = -2147024809;
      goto LABEL_18;
    }
    DoesRegKeyExist = FveBcdUtil::GetCurrentOsGuid(a1, &v20);
    v14 = DoesRegKeyExist;
    if ( DoesRegKeyExist >= 0 )
    {
      v6 = BcdOpenObject(a1, &GUID_WINDOWS_BOOTMGR, &v17);
      DoesRegKeyExist = FromNtStatus(v6);
      v14 = DoesRegKeyExist;
      if ( DoesRegKeyExist >= 0 )
      {
        BcdElementData = FveBcdUtil::GetBcdElementData(v17, 0x24000001u, &v18, &v16);
        DoesRegKeyExist = FromNtStatus(BcdElementData);
        v14 = DoesRegKeyExist;
        if ( DoesRegKeyExist >= 0 )
        {
          if ( (v16 & 0xF) != 0 )
            goto LABEL_3;
          v8 = v16 >> 4;
          for ( i = 0; ; ++i )
          {
            v19 = i;
            if ( i >= v8 )
              break;
            v10 = (struct _GUID *)((char *)v18 + 16 * i);
            IsAssociatedOS = FveBcdUtil::IsAssociatedOS(a1, v10, &v20, v13);
            DoesRegKeyExist = FromNtStatus(IsAssociatedOS);
            v14 = DoesRegKeyExist;
            if ( DoesRegKeyExist < 0 )
              goto LABEL_18;
            v4 = v13[0];
            if ( v13[0] )
            {
              *a2 = *v10;
              break;
            }
          }
          if ( !v4 )
          {
            DoesRegKeyExist = -2147024894;
            v14 = -2147024894;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                73,
                WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
                2147942402LL);
          }
        }
      }
    }
  }
LABEL_18:
  if ( v17 )
    BcdCloseObject(v17);
  if ( v18 )
    operator delete(v18);
  return (unsigned int)DoesRegKeyExist;
}

```

## disassembly

```asm
0x1800da860  mov     r11, rsp
0x1800da863  mov     [r11+18h], rbx
0x1800da867  mov     [r11+20h], rsi
0x1800da86b  push    rdi
0x1800da86c  push    r12
0x1800da86e  push    r13
0x1800da870  push    r14
0x1800da872  push    r15
0x1800da874  sub     rsp, 60h
0x1800da878  mov     rax, cs:__security_cookie
0x1800da87f  xor     rax, rsp
0x1800da882  mov     [rsp+88h+var_30], rax
0x1800da887  mov     r13, rdx
0x1800da88a  mov     r15, rcx
0x1800da88d  xorps   xmm0, xmm0
0x1800da890  movups  xmmword ptr [rsp+88h+var_40.Data1], xmm0
0x1800da895  mov     qword ptr [r11-58h], 0
0x1800da89d  mov     qword ptr [r11-50h], 0
0x1800da8a5  mov     [rsp+88h+var_5C], 0
0x1800da8ad  xor     r14b, r14b
0x1800da8b0  mov     [r11-68h], r14b
0x1800da8b4  mov     [rsp+88h+var_60], 0
0x1800da8bc  lea     r8, [r11-60h]
0x1800da8c0  call    NgscbpDoesRegKeyExist
0x1800da8c5  mov     ebx, eax
0x1800da8c7  mov     [rsp+88h+var_64], eax
0x1800da8cb  test    eax, eax
0x1800da8cd  js      loc_1800DAA09
0x1800da8d3  cmp     [rsp+88h+var_60], 0
0x1800da8d8  jnz     short loc_1800DA8E8
0x1800da8da  mov     ebx, 80070057h
0x1800da8df  mov     [rsp+88h+var_64], ebx
0x1800da8e3  jmp     loc_1800DAA09
0x1800da8e8  lea     rdx, [rsp+88h+var_40]; struct _GUID *
0x1800da8ed  mov     rcx, r15; void *
0x1800da8f0  call    ?GetCurrentOsGuid@FveBcdUtil@@SAJPEAXPEAU_GUID@@@Z; FveBcdUtil::GetCurrentOsGuid(void *,_GUID *)
0x1800da8f5  mov     ebx, eax
0x1800da8f7  mov     [rsp+88h+var_64], eax
0x1800da8fb  test    eax, eax
0x1800da8fd  js      loc_1800DAA09
0x1800da903  lea     r8, [rsp+88h+var_58]
0x1800da908  lea     rdx, GUID_WINDOWS_BOOTMGR
0x1800da90f  mov     rcx, r15
0x1800da912  call    cs:__imp_BcdOpenObject
0x1800da919  nop     dword ptr [rax+rax+00h]
0x1800da91e  mov     ecx, eax; int
0x1800da920  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800da925  mov     ebx, eax
0x1800da927  mov     [rsp+88h+var_64], eax
0x1800da92b  test    eax, eax
0x1800da92d  js      loc_1800DAA09
0x1800da933  lea     r9, [rsp+88h+var_5C]; unsigned int *
0x1800da938  lea     r8, [rsp+88h+var_50]; void **
0x1800da93d  mov     edx, 24000001h; unsigned int
0x1800da942  mov     rcx, [rsp+88h+var_58]; void *
0x1800da947  call    ?GetBcdElementData@FveBcdUtil@@SAJPEAXKPEAPEAXPEAK@Z; FveBcdUtil::GetBcdElementData(void *,ulong,void * *,ulong *)
0x1800da94c  mov     ecx, eax; int
0x1800da94e  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800da953  mov     ebx, eax
0x1800da955  mov     [rsp+88h+var_64], eax
0x1800da959  test    eax, eax
0x1800da95b  js      loc_1800DAA09
0x1800da961  mov     esi, [rsp+88h+var_5C]
0x1800da965  test    sil, 0Fh
0x1800da969  jnz     loc_1800DA8DA
0x1800da96f  shr     esi, 4
0x1800da972  xor     edi, edi
0x1800da974  mov     [rsp+88h+var_48], edi
0x1800da978  cmp     edi, esi
0x1800da97a  jnb     short loc_1800DA9C9
0x1800da97c  mov     r12d, edi
0x1800da97f  shl     r12, 4
0x1800da983  add     r12, [rsp+88h+var_50]
0x1800da988  lea     r9, [rsp+88h+var_68]; unsigned __int8 *
0x1800da98d  lea     r8, [rsp+88h+var_40]; struct _GUID *
0x1800da992  mov     rdx, r12; struct _GUID *
0x1800da995  mov     rcx, r15; void *
0x1800da998  call    ?IsAssociatedOS@FveBcdUtil@@SAJPEAXPEAU_GUID@@1PEAE@Z; FveBcdUtil::IsAssociatedOS(void *,_GUID *,_GUID *,uchar *)
0x1800da99d  mov     ecx, eax; int
0x1800da99f  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800da9a4  mov     ebx, eax
0x1800da9a6  mov     [rsp+88h+var_64], eax
0x1800da9aa  test    eax, eax
0x1800da9ac  js      short loc_1800DAA09
0x1800da9ae  mov     r14b, [rsp+88h+var_68]
0x1800da9b3  test    r14b, r14b
0x1800da9b6  jz      short loc_1800DA9C5
0x1800da9b8  movups  xmm0, xmmword ptr [r12]
0x1800da9bd  movdqu  xmmword ptr [r13+0], xmm0
0x1800da9c3  jmp     short loc_1800DA9C9
0x1800da9c5  inc     edi
0x1800da9c7  jmp     short loc_1800DA974
0x1800da9c9  test    r14b, r14b
0x1800da9cc  jnz     short loc_1800DAA09
0x1800da9ce  mov     ebx, 80070002h
0x1800da9d3  mov     [rsp+88h+var_64], ebx
0x1800da9d7  lea     rax, WPP_GLOBAL_Control
0x1800da9de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da9e5  cmp     rcx, rax
0x1800da9e8  jz      short loc_1800DAA09
0x1800da9ea  test    byte ptr [rcx+1Ch], 2
0x1800da9ee  jz      short loc_1800DAA09
0x1800da9f0  mov     edx, 49h ; 'I'
0x1800da9f5  mov     r9d, ebx
0x1800da9f8  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x1800da9ff  mov     rcx, [rcx+10h]
0x1800daa03  call    WPP_SF_d
0x1800daa08  nop
0x1800daa09  mov     rcx, [rsp+88h+var_58]
0x1800daa0e  test    rcx, rcx
0x1800daa11  jz      short loc_1800DAA1F
0x1800daa13  call    cs:__imp_BcdCloseObject
0x1800daa1a  nop     dword ptr [rax+rax+00h]
0x1800daa1f  mov     rcx, [rsp+88h+var_50]
0x1800daa24  test    rcx, rcx
0x1800daa27  jz      short loc_1800DAA35
0x1800daa29  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800daa30  nop     dword ptr [rax+rax+00h]
0x1800daa35  mov     eax, ebx
0x1800daa37  mov     rcx, [rsp+88h+var_30]
0x1800daa3c  xor     rcx, rsp; StackCookie
0x1800daa3f  call    __security_check_cookie
0x1800daa44  lea     r11, [rsp+88h+var_28]
0x1800daa49  mov     rbx, [r11+40h]
0x1800daa4d  mov     rsi, [r11+48h]
0x1800daa51  mov     rsp, r11
0x1800daa54  pop     r15
0x1800daa56  pop     r14
0x1800daa58  pop     r13
0x1800daa5a  pop     r12
0x1800daa5c  pop     rdi
0x1800daa5d  retn
0x180128a8d  push    rbp
0x180128a8f  sub     rsp, 20h
0x180128a93  mov     rbp, rdx
0x180128a96  mov     rcx, [rbp+30h]
0x180128a9a  test    rcx, rcx
0x180128a9d  jz      short loc_180128AAC
0x180128a9f  call    cs:__imp_BcdCloseObject
0x180128aa6  nop     dword ptr [rax+rax+00h]
0x180128aab  nop
0x180128aac  mov     rcx, [rbp+38h]
0x180128ab0  test    rcx, rcx
0x180128ab3  jz      short loc_180128AC2
0x180128ab5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180128abc  nop     dword ptr [rax+rax+00h]
0x180128ac1  nop
0x180128ac2  add     rsp, 20h
0x180128ac6  pop     rbp
0x180128ac7  retn
```
