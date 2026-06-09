# GetRsrcDirEntry(int,ulong,ushort const *,ulong,_IMAGE_RESOURCE_DIRECTORY_ENTRY *)

- ea: `0x1800586f8`
- end: `0x1800589b8`
- name: `?GetRsrcDirEntry@@YAJHKPEBGKPEAU_IMAGE_RESOURCE_DIRECTORY_ENTRY@@@Z`
- size: `704`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, struct _IMAGE_RESOURCE_DIRECTORY_ENTRY *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180058240`
- `0x180058ad4`

## callees

- `0x180032130`
- `0x180032668`
- `0x180032de0`
- `0x18004d900`
- `0x18004dcf0`
- `0x1800586f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800588ec`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800588ec`

## pseudocode

```c
__int64 __fastcall GetRsrcDirEntry(
        int a1,
        int a2,
        const unsigned __int16 *a3,
        int a4,
        struct _IMAGE_RESOURCE_DIRECTORY_ENTRY *a5)
{
  __int64 result; // rax
  int v10; // ebx
  __int64 v11; // rsi
  int v12; // r12d
  unsigned __int64 v13; // rcx
  unsigned int v14; // eax
  int v15; // esi
  _WORD v16[2]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v17; // [rsp+24h] [rbp-DCh] BYREF
  unsigned int v18; // [rsp+28h] [rbp-D8h] BYREF
  int v19; // [rsp+2Ch] [rbp-D4h]
  __int128 v20; // [rsp+30h] [rbp-D0h] BYREF
  _WORD v21[128]; // [rsp+40h] [rbp-C0h] BYREF

  v19 = a2;
  v17 = 0;
  v18 = 0;
  v16[0] = 0;
  v21[0] = 0;
  v20 = 0;
  result = HrCurPos(a1, &v18);
  if ( (int)result < 0 )
    return result;
  v10 = HrSeek(a1, a2, 0);
  if ( v10 >= 0 )
  {
    v10 = HrRead(a1, &v20, 0x10u);
    if ( v10 >= 0 )
    {
      if ( !a3 )
      {
        v10 = HrSeek(a1, 8 * (unsigned int)WORD6(v20), 1);
        if ( v10 < 0 )
          goto LABEL_28;
        v15 = 0;
        if ( HIWORD(v20) )
        {
          while ( 1 )
          {
            v10 = HrRead(a1, a5, 8u);
            if ( v10 < 0 )
              goto LABEL_28;
            if ( (a5->Name & 0x80000000) != 0 )
              goto LABEL_27;
            if ( a5->Name == a4 )
              goto LABEL_11;
            if ( ++v15 == HIWORD(v20) )
              goto LABEL_27;
          }
        }
        goto LABEL_27;
      }
      v11 = -1;
      do
        ++v11;
      while ( a3[v11] );
      if ( (_WORD)v11 == 1 )
      {
        if ( *a3 == 42 && HIDWORD(v20) )
        {
          v10 = HrRead(a1, a5, 8u);
          if ( v10 >= 0 )
LABEL_11:
            v10 = 0;
          goto LABEL_28;
        }
LABEL_14:
        v12 = 0;
        if ( WORD6(v20) )
        {
          do
          {
            v10 = HrRead(a1, a5, 8u);
            if ( v10 < 0 )
              goto LABEL_28;
            if ( (a5->Name & 0x80000000) == 0 )
              break;
            v10 = HrCurPos(a1, &v17);
            if ( v10 < 0 )
              goto LABEL_28;
            v10 = HrSeek(a1, v19 + (a5->Name & 0x7FFFFFFF), 0);
            if ( v10 < 0 )
              goto LABEL_28;
            v10 = HrRead(a1, v16, 2u);
            if ( v10 < 0 )
              goto LABEL_28;
            if ( v16[0] == (_WORD)v11 )
            {
              v10 = HrRead(a1, v21, 2 * (unsigned int)v16[0]);
              if ( v10 < 0 )
                goto LABEL_28;
              v13 = 2LL * v16[0];
              if ( v13 >= 0x100 )
                _report_rangecheckfailure(v13, 0);
              v21[v16[0]] = 0;
            }
            v10 = HrSeek(a1, v17, 0);
            if ( v10 < 0 )
              goto LABEL_28;
            if ( !(unsigned int)_o__wcsicmp(v21, a3) )
              goto LABEL_11;
          }
          while ( ++v12 != WORD6(v20) );
        }
LABEL_27:
        v10 = -2147312566;
        goto LABEL_28;
      }
      if ( (unsigned __int16)v11 < 0x80u )
        goto LABEL_14;
      v10 = -2147024809;
    }
  }
LABEL_28:
  v14 = HrSeek(a1, v18, 0);
  if ( !v10 )
    return v14;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800586f8  mov     [rsp-8+arg_18], rbx
0x1800586fd  push    rbp
0x1800586fe  push    rsi
0x1800586ff  push    rdi
0x180058700  push    r12
0x180058702  push    r13
0x180058704  push    r14
0x180058706  push    r15
0x180058708  lea     rbp, [rsp-50h]
0x18005870d  sub     rsp, 150h
0x180058714  mov     rax, cs:__security_cookie
0x18005871b  xor     rax, rsp
0x18005871e  mov     [rbp+80h+var_40], rax
0x180058722  mov     r15, [rbp+80h+arg_20]
0x180058729  mov     edi, ecx
0x18005872b  xor     ecx, ecx
0x18005872d  mov     [rsp+180h+var_154], edx
0x180058731  mov     [rsp+180h+var_15C], ecx
0x180058735  mov     ebx, edx
0x180058737  mov     [rsp+180h+var_158], ecx
0x18005873b  lea     rdx, [rsp+180h+var_158]; unsigned int *
0x180058740  mov     [rsp+180h+var_160], cx
0x180058745  xorps   xmm0, xmm0
0x180058748  mov     [rsp+180h+var_140], cx
0x18005874d  mov     r12d, r9d
0x180058750  mov     ecx, edi; int
0x180058752  mov     r13, r8
0x180058755  movups  [rsp+180h+var_150], xmm0
0x18005875a  call    ?HrCurPos@@YAJHPEAK@Z; HrCurPos(int,ulong *)
0x18005875f  test    eax, eax
0x180058761  js      loc_180058927
0x180058767  xor     r8d, r8d; int
0x18005876a  mov     edx, ebx; int
0x18005876c  mov     ecx, edi; int
0x18005876e  call    ?HrSeek@@YAJHJH@Z; HrSeek(int,long,int)
0x180058773  mov     ebx, eax
0x180058775  test    eax, eax
0x180058777  js      loc_180058912
0x18005877d  mov     r8d, 10h; unsigned int
0x180058783  lea     rdx, [rsp+180h+var_150]; void *
0x180058788  mov     ecx, edi; int
0x18005878a  call    ?HrRead@@YAJHPEAXI@Z; HrRead(int,void *,uint)
0x18005878f  xor     edx, edx
0x180058791  mov     ebx, eax
0x180058793  test    eax, eax
0x180058795  js      loc_180058912
0x18005879b  test    r13, r13
0x18005879e  jz      loc_18005894E
0x1800587a4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800587a8  inc     rsi
0x1800587ab  cmp     [r13+rsi*2+0], dx
0x1800587b1  jnz     short loc_1800587A8
0x1800587b3  movzx   ecx, word ptr [rsp+180h+var_150+0Ch]
0x1800587b8  mov     r14d, 1
0x1800587be  cmp     si, r14w
0x1800587c2  jnz     short loc_1800587FB
0x1800587c4  cmp     word ptr [r13+0], 2Ah ; '*'
0x1800587ca  jnz     short loc_18005880F
0x1800587cc  test    cx, cx
0x1800587cf  jnz     short loc_1800587D8
0x1800587d1  cmp     word ptr [rsp+180h+var_150+0Eh], dx
0x1800587d6  jbe     short loc_18005880F
0x1800587d8  mov     r8d, 8; unsigned int
0x1800587de  mov     rdx, r15; void *
0x1800587e1  mov     ecx, edi; int
0x1800587e3  call    ?HrRead@@YAJHPEAXI@Z; HrRead(int,void *,uint)
0x1800587e8  xor     edx, edx
0x1800587ea  mov     ebx, eax
0x1800587ec  test    eax, eax
0x1800587ee  js      loc_180058912
0x1800587f4  mov     ebx, edx
0x1800587f6  jmp     loc_180058912
0x1800587fb  mov     eax, 80h
0x180058800  cmp     si, ax
0x180058803  jb      short loc_18005880F
0x180058805  mov     ebx, 80070057h
0x18005880a  jmp     loc_180058912
0x18005880f  mov     r12d, edx
0x180058812  cmp     dx, cx
0x180058815  jz      loc_18005890D
0x18005881b  mov     r8d, 8; unsigned int
0x180058821  mov     rdx, r15; void *
0x180058824  mov     ecx, edi; int
0x180058826  call    ?HrRead@@YAJHPEAXI@Z; HrRead(int,void *,uint)
0x18005882b  mov     ebx, eax
0x18005882d  xor     eax, eax
0x18005882f  test    ebx, ebx
0x180058831  js      loc_180058912
0x180058837  cmp     [r15], eax
0x18005883a  jge     loc_18005890D
0x180058840  lea     rdx, [rsp+180h+var_15C]; unsigned int *
0x180058845  mov     ecx, edi; int
0x180058847  call    ?HrCurPos@@YAJHPEAK@Z; HrCurPos(int,ulong *)
0x18005884c  mov     ebx, eax
0x18005884e  test    eax, eax
0x180058850  js      loc_180058912
0x180058856  mov     edx, [r15]
0x180058859  xor     r8d, r8d; int
0x18005885c  btr     edx, 1Fh
0x180058860  mov     ecx, edi; int
0x180058862  add     edx, [rsp+180h+var_154]; int
0x180058866  call    ?HrSeek@@YAJHJH@Z; HrSeek(int,long,int)
0x18005886b  mov     ebx, eax
0x18005886d  test    eax, eax
0x18005886f  js      loc_180058912
0x180058875  mov     r8d, 2; unsigned int
0x18005887b  lea     rdx, [rsp+180h+var_160]; void *
0x180058880  mov     ecx, edi; int
0x180058882  call    ?HrRead@@YAJHPEAXI@Z; HrRead(int,void *,uint)
0x180058887  mov     ebx, eax
0x180058889  test    eax, eax
0x18005888b  js      loc_180058912
0x180058891  cmp     [rsp+180h+var_160], si
0x180058896  jnz     short loc_1800588D0
0x180058898  movzx   r8d, [rsp+180h+var_160]
0x18005889e  lea     rdx, [rsp+180h+var_140]; void *
0x1800588a3  add     r8d, r8d; unsigned int
0x1800588a6  mov     ecx, edi; int
0x1800588a8  call    ?HrRead@@YAJHPEAXI@Z; HrRead(int,void *,uint)
0x1800588ad  xor     edx, edx
0x1800588af  mov     ebx, eax
0x1800588b1  test    eax, eax
0x1800588b3  js      short loc_180058912
0x1800588b5  movzx   eax, [rsp+180h+var_160]
0x1800588ba  lea     rcx, [rax+rax]
0x1800588be  cmp     rcx, 100h
0x1800588c5  jnb     loc_1800589B2
0x1800588cb  mov     [rsp+rcx+180h+var_140], dx
0x1800588d0  mov     edx, [rsp+180h+var_15C]; int
0x1800588d4  xor     r8d, r8d; int
0x1800588d7  mov     ecx, edi; int
0x1800588d9  call    ?HrSeek@@YAJHJH@Z; HrSeek(int,long,int)
0x1800588de  mov     ebx, eax
0x1800588e0  test    eax, eax
0x1800588e2  js      short loc_180058912
0x1800588e4  mov     rdx, r13
0x1800588e7  lea     rcx, [rsp+180h+var_140]
0x1800588ec  call    cs:__imp__o__wcsicmp
0x1800588f2  xor     edx, edx
0x1800588f4  test    eax, eax
0x1800588f6  jz      loc_1800587F4
0x1800588fc  movzx   eax, word ptr [rsp+180h+var_150+0Ch]
0x180058901  add     r12d, r14d
0x180058904  cmp     r12d, eax
0x180058907  jnz     loc_18005881B
0x18005890d  mov     ebx, 80029C4Ah
0x180058912  mov     edx, [rsp+180h+var_158]; int
0x180058916  xor     r8d, r8d; int
0x180058919  mov     ecx, edi; int
0x18005891b  call    ?HrSeek@@YAJHJH@Z; HrSeek(int,long,int)
0x180058920  test    ebx, ebx
0x180058922  cmovz   ebx, eax
0x180058925  mov     eax, ebx
0x180058927  mov     rcx, [rbp+80h+var_40]
0x18005892b  xor     rcx, rsp; StackCookie
0x18005892e  call    __security_check_cookie
0x180058933  mov     rbx, [rsp+180h+arg_18]
0x18005893b  add     rsp, 150h
0x180058942  pop     r15
0x180058944  pop     r14
0x180058946  pop     r13
0x180058948  pop     r12
0x18005894a  pop     rdi
0x18005894b  pop     rsi
0x18005894c  pop     rbp
0x18005894d  retn
0x18005894e  movzx   edx, word ptr [rsp+180h+var_150+0Ch]
0x180058953  mov     r14d, 1
0x180058959  shl     edx, 3; int
0x18005895c  mov     r8d, r14d; int
0x18005895f  mov     ecx, edi; int
0x180058961  call    ?HrSeek@@YAJHJH@Z; HrSeek(int,long,int)
0x180058966  xor     edx, edx
0x180058968  mov     ebx, eax
0x18005896a  test    eax, eax
0x18005896c  js      short loc_180058912
0x18005896e  mov     esi, edx
0x180058970  cmp     dx, word ptr [rsp+180h+var_150+0Eh]
0x180058975  jz      short loc_18005890D
0x180058977  mov     r8d, 8; unsigned int
0x18005897d  mov     rdx, r15; void *
0x180058980  mov     ecx, edi; int
0x180058982  call    ?HrRead@@YAJHPEAXI@Z; HrRead(int,void *,uint)
0x180058987  xor     edx, edx
0x180058989  mov     ebx, eax
0x18005898b  test    eax, eax
0x18005898d  js      short loc_180058912
0x18005898f  cmp     [r15], edx
0x180058992  jl      loc_18005890D
0x180058998  cmp     [r15], r12d
0x18005899b  jz      loc_1800587F4
0x1800589a1  movzx   eax, word ptr [rsp+180h+var_150+0Eh]
0x1800589a6  add     esi, r14d
0x1800589a9  cmp     esi, eax
0x1800589ab  jnz     short loc_180058977
0x1800589ad  jmp     loc_18005890D
0x1800589b2  call    __report_rangecheckfailure
```
