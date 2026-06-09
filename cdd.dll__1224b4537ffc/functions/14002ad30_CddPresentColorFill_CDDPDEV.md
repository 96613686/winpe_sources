# CddPresentColorFill(CDDPDEV *)

- ea: `0x14002ad30`
- end: `0x14002b0a3`
- name: `?CddPresentColorFill@@YAJPEAUCDDPDEV@@@Z`
- size: `883`
- prototype: `__int64 __fastcall(struct CDDPDEV *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140011510`

## callees

- `0x14002ad30`
- `0x1400371f0`
- `0x1400372d0`
- `0x140037640`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002b04f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002b04f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14002adcb`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14002adcb`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002adf9`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002adf9`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002ae8a`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002af37`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002ae8a`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002af37`
- `watchdog!WdLogSingleEntry0` at `0x14002ade2`
- `watchdog!WdLogSingleEntry0` at `0x14002ae71`
- `watchdog!WdLogSingleEntry0` at `0x14002af21`
- `watchdog!WdLogSingleEntry0` at `0x14002ade2`
- `watchdog!WdLogSingleEntry0` at `0x14002ae71`
- `watchdog!WdLogSingleEntry0` at `0x14002af21`
- `WIN32K!CLIPOBJ_bEnum` at `0x14002aefd`
- `WIN32K!CLIPOBJ_bEnum` at `0x14002aefd`
- `WIN32K!CLIPOBJ_cEnumStart` at `0x14002aed9`
- `WIN32K!CLIPOBJ_cEnumStart` at `0x14002aed9`

## pseudocode

```c
__int64 __fastcall CddPresentColorFill(struct CDDPDEV *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  char *v4; // rdi
  _QWORD *v5; // rax
  __int64 result; // rax
  int v7; // r15d
  char v8; // cl
  char *v9; // r13
  BOOL v10; // r12d
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  unsigned int i; // r8d
  int v14; // r11d
  int v15; // r10d
  int v16; // r9d
  int v17; // edx
  unsigned int (__fastcall *v18)(_QWORD *); // rax
  _QWORD v19[12]; // [rsp+30h] [rbp-49h] BYREF

  memset(v19, 0, 0x58u);
  v2 = *((_QWORD *)a1 + 349);
  v19[1] = *((_QWORD *)a1 + 311);
  LODWORD(v19[2]) = *((_DWORD *)a1 + 196);
  HIDWORD(v19[2]) = *((_DWORD *)a1 + 696);
  v19[3] = *(_QWORD *)(v2 + 48);
  v19[4] = *(_QWORD *)((char *)a1 + 796);
  LODWORD(v19[5]) = *(_DWORD *)(v2 + 64);
  v3 = *((_QWORD *)a1 + 345);
  if ( v3 && *(_BYTE *)(v3 + 20) )
  {
    v4 = (char *)ExAllocateFromLookasideListEx(*((PLOOKASIDE_LIST_EX *)a1 + 97));
    if ( !v4 )
    {
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 3248;
      v5 = (_QWORD *)WdLogNewEntry5_WdLowResource();
      v5[3] = gCddImageInfo;
      v5[4] = (unsigned int)dword_14003E570;
      v5[5] = 215857758;
      result = 3221225495LL;
      WdLogGlobalForLineNumber = 3248;
      return result;
    }
    v7 = 0;
    v8 = *(_BYTE *)(*((_QWORD *)a1 + 345) + 20LL);
    if ( v8 == 1 )
    {
      *(_DWORD *)v4 = 1;
      v9 = v4 + 4;
      v10 = 0;
      *(_OWORD *)(v4 + 4) = *(_OWORD *)(*((_QWORD *)a1 + 345) + 4LL);
    }
    else
    {
      if ( v8 != 3 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 3262;
        v11 = (_QWORD *)WdLogNewEntry5_WdAssertion();
        v11[3] = gCddImageInfo;
        v11[4] = (unsigned int)dword_14003E570;
        v11[5] = 215857758;
        WdLogGlobalForLineNumber = 3262;
      }
      v10 = 1;
      CLIPOBJ_cEnumStart(*((CLIPOBJ **)a1 + 345), 0, 0, 4u, 0x14u);
      v9 = v4 + 4;
    }
    if ( !v10 )
      goto LABEL_12;
    do
    {
      v10 = CLIPOBJ_bEnum(*((CLIPOBJ **)a1 + 345), 0x144u, (ULONG *)v4);
LABEL_12:
      HIDWORD(v19[9]) = 0;
      v19[10] = v9;
      if ( *(_DWORD *)v4 > 0x14u )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 3280;
        v12 = (_QWORD *)WdLogNewEntry5_WdAssertion();
        v12[3] = gCddImageInfo;
        v12[4] = (unsigned int)dword_14003E570;
        v12[5] = 215857758;
        WdLogGlobalForLineNumber = 3280;
      }
      for ( i = 0; i < *(_DWORD *)v4; ++i )
      {
        v14 = **((_DWORD **)a1 + 346);
        if ( *(_DWORD *)&v4[16 * i + 4] >= v14 )
          v14 = *(_DWORD *)&v4[16 * i + 4];
        else
          *(_DWORD *)&v4[16 * i + 4] = v14;
        v15 = *(_DWORD *)(*((_QWORD *)a1 + 346) + 8LL);
        if ( *(_DWORD *)&v4[16 * i + 12] <= v15 )
          v15 = *(_DWORD *)&v4[16 * i + 12];
        else
          *(_DWORD *)&v4[16 * i + 12] = v15;
        v16 = *(_DWORD *)(*((_QWORD *)a1 + 346) + 4LL);
        if ( *(_DWORD *)&v4[16 * i + 8] >= v16 )
          v16 = *(_DWORD *)&v4[16 * i + 8];
        else
          *(_DWORD *)&v4[16 * i + 8] = v16;
        v17 = *(_DWORD *)(*((_QWORD *)a1 + 346) + 12LL);
        if ( *(_DWORD *)&v4[16 * i + 16] <= v17 )
          v17 = *(_DWORD *)&v4[16 * i + 16];
        else
          *(_DWORD *)&v4[16 * i + 16] = v17;
        if ( v16 < v17 && v14 < v15 )
        {
          if ( HIDWORD(v19[9]) < i )
            *(_OWORD *)&v4[16 * HIDWORD(v19[9]) + 4] = *(_OWORD *)&v4[16 * i + 4];
          ++HIDWORD(v19[9]);
        }
      }
      if ( HIDWORD(v19[9]) )
      {
        v7 = (*((__int64 (__fastcall **)(_QWORD *))a1 + 51))(v19);
        if ( v7 < 0 )
          break;
      }
    }
    while ( v10 );
    ExFreeToLookasideListEx(*((PLOOKASIDE_LIST_EX *)a1 + 97), v4);
  }
  else
  {
    v19[10] = *((_QWORD *)a1 + 346);
    v18 = (unsigned int (__fastcall *)(_QWORD *))*((_QWORD *)a1 + 51);
    HIDWORD(v19[9]) = 1;
    return v18(v19);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14002ad30  push    rbp
0x14002ad32  push    rbx
0x14002ad33  push    rdi
0x14002ad34  push    r12
0x14002ad36  push    r13
0x14002ad38  push    r15
0x14002ad3a  lea     rbp, [rsp-2Fh]
0x14002ad3f  sub     rsp, 0A8h
0x14002ad46  mov     rax, cs:__security_cookie
0x14002ad4d  xor     rax, rsp
0x14002ad50  mov     [rbp+57h+var_40], rax
0x14002ad54  xor     edx, edx; Val
0x14002ad56  mov     rbx, rcx
0x14002ad59  lea     rcx, [rbp+57h+var_A0]; void *
0x14002ad5d  lea     r8d, [rdx+58h]; Size
0x14002ad61  call    memset
0x14002ad66  mov     rax, [rbx+9B8h]
0x14002ad6d  mov     rcx, [rbx+0AE8h]
0x14002ad74  mov     [rbp+57h+var_98], rax
0x14002ad78  mov     eax, [rbx+310h]
0x14002ad7e  mov     [rbp+57h+var_90], eax
0x14002ad81  mov     eax, [rbx+0AE0h]
0x14002ad87  mov     [rbp+57h+var_8C], eax
0x14002ad8a  mov     rax, [rcx+30h]
0x14002ad8e  mov     [rbp+57h+var_88], rax
0x14002ad92  mov     eax, [rbx+31Ch]
0x14002ad98  mov     [rbp+57h+var_80], eax
0x14002ad9b  mov     eax, [rbx+320h]
0x14002ada1  mov     [rbp+57h+var_7C], eax
0x14002ada4  mov     eax, [rcx+40h]
0x14002ada7  mov     [rbp+57h+var_78], eax
0x14002adaa  mov     rax, [rbx+0AC8h]
0x14002adb1  test    rax, rax
0x14002adb4  jz      loc_14002B05D
0x14002adba  cmp     byte ptr [rax+14h], 0
0x14002adbe  jz      loc_14002B05D
0x14002adc4  mov     rcx, [rbx+308h]; Lookaside
0x14002adcb  call    cs:__imp_ExAllocateFromLookasideListEx
0x14002add2  nop     dword ptr [rax+rax+00h]
0x14002add7  mov     rdi, rax
0x14002adda  test    rax, rax
0x14002addd  jnz     short loc_14002AE32
0x14002addf  lea     ecx, [rax+6]
0x14002ade2  call    cs:__imp_WdLogSingleEntry0
0x14002ade9  nop     dword ptr [rax+rax+00h]
0x14002adee  mov     ebx, 0CB0h
0x14002adf3  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002adf9  call    cs:__imp_WdLogNewEntry5_WdLowResource
0x14002ae00  nop     dword ptr [rax+rax+00h]
0x14002ae05  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002ae0c  mov     [rax+18h], rcx
0x14002ae10  mov     ecx, cs:dword_14003E570
0x14002ae16  mov     [rax+20h], rcx
0x14002ae1a  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002ae22  mov     eax, 0C0000017h
0x14002ae27  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002ae2d  jmp     loc_14002B085
0x14002ae32  mov     rax, [rbx+0AC8h]
0x14002ae39  xor     r15d, r15d
0x14002ae3c  mov     cl, [rax+14h]
0x14002ae3f  cmp     cl, 1
0x14002ae42  jnz     short loc_14002AE67
0x14002ae44  mov     dword ptr [rdi], 1
0x14002ae4a  lea     r13, [rdi+4]
0x14002ae4e  mov     rax, [rbx+0AC8h]
0x14002ae55  xor     r12d, r12d
0x14002ae58  movups  xmm0, xmmword ptr [rax+4]
0x14002ae5c  movdqu  xmmword ptr [r13+0], xmm0
0x14002ae62  jmp     loc_14002AEE9
0x14002ae67  cmp     cl, 3
0x14002ae6a  jz      short loc_14002AEBA
0x14002ae6c  mov     ecx, 1
0x14002ae71  call    cs:__imp_WdLogSingleEntry0
0x14002ae78  nop     dword ptr [rax+rax+00h]
0x14002ae7d  mov     r12d, 0CBEh
0x14002ae83  mov     cs:WdLogGlobalForLineNumber, r12d
0x14002ae8a  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14002ae91  nop     dword ptr [rax+rax+00h]
0x14002ae96  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002ae9d  mov     [rax+18h], rcx
0x14002aea1  mov     ecx, cs:dword_14003E570
0x14002aea7  mov     [rax+20h], rcx
0x14002aeab  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002aeb3  mov     cs:WdLogGlobalForLineNumber, r12d
0x14002aeba  mov     rcx, [rbx+0AC8h]; pco
0x14002aec1  mov     r12d, 1
0x14002aec7  xor     r8d, r8d; iType
0x14002aeca  mov     [rsp+0D0h+cLimit], 14h; cLimit
0x14002aed2  xor     edx, edx; bAll
0x14002aed4  lea     r9d, [r12+3]; iDirection
0x14002aed9  call    cs:__imp_CLIPOBJ_cEnumStart
0x14002aee0  nop     dword ptr [rax+rax+00h]
0x14002aee5  lea     r13, [rdi+4]
0x14002aee9  test    r12d, r12d
0x14002aeec  jz      short loc_14002AF0C
0x14002aeee  mov     rcx, [rbx+0AC8h]; pco
0x14002aef5  mov     r8, rdi; pul
0x14002aef8  mov     edx, 144h; cj
0x14002aefd  call    cs:__imp_CLIPOBJ_bEnum
0x14002af04  nop     dword ptr [rax+rax+00h]
0x14002af09  mov     r12d, eax
0x14002af0c  mov     [rbp+57h+var_54], 0
0x14002af13  mov     [rbp+57h+var_50], r13
0x14002af17  cmp     dword ptr [rdi], 14h
0x14002af1a  jbe     short loc_14002AF6A
0x14002af1c  mov     ecx, 1
0x14002af21  call    cs:__imp_WdLogSingleEntry0
0x14002af28  nop     dword ptr [rax+rax+00h]
0x14002af2d  mov     cs:WdLogGlobalForLineNumber, 0CD0h
0x14002af37  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14002af3e  nop     dword ptr [rax+rax+00h]
0x14002af43  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002af4a  mov     [rax+18h], rcx
0x14002af4e  mov     ecx, cs:dword_14003E570
0x14002af54  mov     [rax+20h], rcx
0x14002af58  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002af60  mov     cs:WdLogGlobalForLineNumber, 0CD0h
0x14002af6a  xor     r8d, r8d
0x14002af6d  cmp     [rdi], r8d
0x14002af70  jbe     loc_14002B01F
0x14002af76  mov     rax, [rbx+0AD0h]
0x14002af7d  mov     ecx, r8d
0x14002af80  add     rcx, rcx
0x14002af83  mov     r11d, [rax]
0x14002af86  mov     eax, [rdi+rcx*8+4]
0x14002af8a  cmp     eax, r11d
0x14002af8d  jge     short loc_14002AF96
0x14002af8f  mov     [rdi+rcx*8+4], r11d
0x14002af94  jmp     short loc_14002AF99
0x14002af96  mov     r11d, eax
0x14002af99  mov     rax, [rbx+0AD0h]
0x14002afa0  mov     r10d, [rax+8]
0x14002afa4  mov     eax, [rdi+rcx*8+0Ch]
0x14002afa8  cmp     eax, r10d
0x14002afab  jle     short loc_14002AFB4
0x14002afad  mov     [rdi+rcx*8+0Ch], r10d
0x14002afb2  jmp     short loc_14002AFB7
0x14002afb4  mov     r10d, eax
0x14002afb7  mov     rax, [rbx+0AD0h]
0x14002afbe  mov     r9d, [rax+4]
0x14002afc2  mov     eax, [rdi+rcx*8+8]
0x14002afc6  cmp     eax, r9d
0x14002afc9  jge     short loc_14002AFD2
0x14002afcb  mov     [rdi+rcx*8+8], r9d
0x14002afd0  jmp     short loc_14002AFD5
0x14002afd2  mov     r9d, eax
0x14002afd5  mov     rax, [rbx+0AD0h]
0x14002afdc  mov     edx, [rax+0Ch]
0x14002afdf  mov     eax, [rdi+rcx*8+10h]
0x14002afe3  cmp     eax, edx
0x14002afe5  jle     short loc_14002AFED
0x14002afe7  mov     [rdi+rcx*8+10h], edx
0x14002afeb  jmp     short loc_14002AFEF
0x14002afed  mov     edx, eax
0x14002afef  cmp     r9d, edx
0x14002aff2  jge     short loc_14002B013
0x14002aff4  cmp     r11d, r10d
0x14002aff7  jge     short loc_14002B013
0x14002aff9  cmp     [rbp+57h+var_54], r8d
0x14002affd  jnb     short loc_14002B010
0x14002afff  mov     eax, [rbp+57h+var_54]
0x14002b002  movups  xmm0, xmmword ptr [rdi+rcx*8+4]
0x14002b007  add     rax, rax
0x14002b00a  movdqu  xmmword ptr [rdi+rax*8+4], xmm0
0x14002b010  inc     [rbp+57h+var_54]
0x14002b013  inc     r8d
0x14002b016  cmp     r8d, [rdi]
0x14002b019  jb      loc_14002AF76
0x14002b01f  cmp     [rbp+57h+var_54], 0
0x14002b023  jbe     short loc_14002B03C
0x14002b025  mov     rax, [rbx+198h]
0x14002b02c  lea     rcx, [rbp+57h+var_A0]
0x14002b030  call    _guard_dispatch_icall
0x14002b035  mov     r15d, eax
0x14002b038  test    eax, eax
0x14002b03a  js      short loc_14002B045
0x14002b03c  test    r12d, r12d
0x14002b03f  jnz     loc_14002AEEE
0x14002b045  mov     rcx, [rbx+308h]; Lookaside
0x14002b04c  mov     rdx, rdi; Entry
0x14002b04f  call    cs:__imp_ExFreeToLookasideListEx
0x14002b056  nop     dword ptr [rax+rax+00h]
0x14002b05b  jmp     short loc_14002B082
0x14002b05d  mov     rax, [rbx+0AD0h]
0x14002b064  lea     rcx, [rbp+57h+var_A0]
0x14002b068  mov     [rbp+57h+var_50], rax
0x14002b06c  mov     rax, [rbx+198h]
0x14002b073  mov     [rbp+57h+var_54], 1
0x14002b07a  call    _guard_dispatch_icall
0x14002b07f  mov     r15d, eax
0x14002b082  mov     eax, r15d
0x14002b085  mov     rcx, [rbp+57h+var_40]
0x14002b089  xor     rcx, rsp; StackCookie
0x14002b08c  call    __security_check_cookie
0x14002b091  add     rsp, 0A8h
0x14002b098  pop     r15
0x14002b09a  pop     r13
0x14002b09c  pop     r12
0x14002b09e  pop     rdi
0x14002b09f  pop     rbx
0x14002b0a0  pop     rbp
0x14002b0a1  retn
```
