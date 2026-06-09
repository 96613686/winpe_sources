# GmsapParseAccountNamesLocally(_tagGMsaListEntry *,_UNICODE_STRING const *,_UNICODE_STRING const *,ushort * *,ushort * *,ushort * *,int *)

- ea: `0x18000461c`
- end: `0x180004bb6`
- name: `?GmsapParseAccountNamesLocally@@YAJPEAU_tagGMsaListEntry@@PEBU_UNICODE_STRING@@1PEAPEAG22PEAH@Z`
- size: `1434`
- prototype: `int(struct _tagGMsaListEntry *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, int *)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800025b0`
- `0x1800036c0`
- `0x1800056d0`

## callees

- `0x1800031b0`
- `0x180003500`
- `0x18000461c`
- `0x1800052d0`
- `0x180006280`
- `0x1800062b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000475a`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180004826`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000475a`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180004826`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800049a3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800049a3`
- `ntdll!RtlInitUnicodeString` at `0x180004797`
- `ntdll!RtlInitUnicodeString` at `0x180004891`
- `ntdll!RtlInitUnicodeString` at `0x180004797`
- `ntdll!RtlInitUnicodeString` at `0x180004891`

## pseudocode

```c
__int64 __fastcall GmsapParseAccountNamesLocally(
        struct _tagGMsaListEntry *a1,
        const struct _UNICODE_STRING *a2,
        const struct _UNICODE_STRING *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6,
        int *a7)
{
  int v7; // r13d
  unsigned __int16 *v8; // r12
  unsigned __int16 *v13; // rax
  unsigned int v14; // ebx
  int v15; // eax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  wchar_t *v19; // rax
  const WCHAR *v20; // rbx
  int v21; // eax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r9
  wchar_t *v25; // rax
  const WCHAR *v26; // rbx
  __int64 v27; // rbx
  unsigned __int64 v28; // r15
  unsigned int v29; // r14d
  __int64 v30; // rsi
  unsigned __int64 v31; // rax
  unsigned __int16 *v32; // rax
  unsigned __int16 *v33; // rax
  unsigned __int16 *v34; // rdx
  unsigned __int16 *v35; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-28h] BYREF
  UNICODE_STRING SourceString; // [rsp+38h] [rbp-18h] BYREF

  v7 = 0;
  SourceString = 0;
  v8 = 0;
  DestinationString = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x13u, &WPP_70b8577d707437755865c965214ce19a_Traceguids);
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  *a7 = 1;
  if ( a1 )
  {
    *a4 = (unsigned __int16 *)*((_QWORD *)a1 + 2);
    v13 = (unsigned __int16 *)*((_QWORD *)a1 + 3);
    v14 = 0;
    *a6 = v13;
    *a7 = 0;
    goto LABEL_82;
  }
  v15 = GmsapDuplicateWStr(a2);
  v14 = v15;
  if ( v15 < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v17 = 20;
LABEL_10:
      v18 = (unsigned int)v15;
LABEL_11:
      WPP_SF_D(v16[2], v17, &WPP_70b8577d707437755865c965214ce19a_Traceguids, v18);
      goto LABEL_82;
    }
    goto LABEL_82;
  }
  v15 = GmsapDuplicateWStr(a3);
  v14 = v15;
  if ( v15 >= 0 )
  {
    v19 = wcsrchr(0, 0x40u);
    if ( v19 )
    {
      v20 = v19 + 1;
      *v19 = 0;
      if ( v19[1] && MEMORY[0] )
      {
        GmsapFreeStringRoutine(0);
        RtlInitUnicodeString(&DestinationString, v20);
        v21 = GmsapDuplicateWStr(&DestinationString);
        v14 = v21;
        if ( v21 < 0 )
        {
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            goto LABEL_82;
          v23 = 23;
LABEL_24:
          v24 = (unsigned int)v21;
          goto LABEL_81;
        }
LABEL_38:
        if ( (int)GmsapDuplicateWStr(&::SourceString) < 0 )
        {
          v14 = -1073741801;
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            goto LABEL_82;
          v23 = 26;
          v24 = 3221225495LL;
          goto LABEL_81;
        }
        v27 = -1;
        do
          ++v27;
        while ( *(_WORD *)(2 * v27) );
        v28 = (unsigned int)(v27 - 1);
        if ( *(_WORD *)(2 * v28) == 36 )
        {
          v29 = v27;
          v7 = 1;
        }
        else
        {
          v29 = v27 + 2;
          if ( (unsigned int)v27 >= 0xFFFFFFFE )
          {
            v14 = -1073741675;
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
              goto LABEL_82;
            v23 = 27;
            goto LABEL_80;
          }
        }
        v30 = v29;
        v31 = 2LL * v29;
        if ( v31 <= 0xFFFFFFFF )
        {
          v32 = (unsigned __int16 *)LocalAlloc(0x40u, (unsigned int)v31);
          v8 = v32;
          if ( !v32 )
          {
            v14 = -1073741801;
            goto LABEL_82;
          }
          if ( v29 == (_DWORD)v27 )
          {
            if ( v29 )
            {
              if ( v29 > 0x7FFFFFFFuLL || v28 > 0x7FFFFFFE )
              {
                v14 = -1073741811;
                *v32 = 0;
              }
              else
              {
                v33 = 0;
                v34 = v8;
                do
                {
                  if ( !v28 )
                    break;
                  if ( !*v33 )
                    break;
                  *v34++ = *v33++;
                  --v28;
                  --v30;
                }
                while ( v30 );
                v35 = v34 - 1;
                v14 = v30 == 0 ? 0x80000005 : 0;
                if ( v30 )
                  v35 = v34;
                *v35 = 0;
                if ( v30 )
                  goto LABEL_62;
              }
            }
            else
            {
              v14 = -1073741811;
            }
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
              goto LABEL_82;
            v23 = 29;
            v24 = v14;
LABEL_81:
            WPP_SF_D(v22[2], v23, &WPP_70b8577d707437755865c965214ce19a_Traceguids, v24);
            goto LABEL_82;
          }
          v21 = RtlStringCchPrintfW(v32, v29, L"%ws$", 0);
          v14 = v21;
          if ( v21 < 0 )
          {
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
              goto LABEL_82;
            v23 = 30;
            goto LABEL_24;
          }
LABEL_62:
          if ( v7 )
          {
            *a4 = v8;
            *a5 = 0;
          }
          else
          {
            *a4 = 0;
            *a5 = v8;
          }
          v8 = 0;
          v14 = 0;
          *a6 = 0;
          goto LABEL_82;
        }
        v14 = -1073741675;
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_82;
        v23 = 28;
LABEL_80:
        v24 = 3221225621LL;
        goto LABEL_81;
      }
      v14 = -1073741726;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_82;
      v23 = 22;
    }
    else
    {
      v25 = wcsrchr(0, 0x5Cu);
      if ( !v25 )
        goto LABEL_38;
      v26 = v25 + 1;
      *v25 = 0;
      GmsapFreeStringRoutine(0);
      if ( *v26 )
      {
        RtlInitUnicodeString(&SourceString, v26);
        if ( (int)GmsapDuplicateWStr(&SourceString) < 0 )
        {
          v14 = -1073741801;
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v17 = 25;
            v18 = 3221225495LL;
            goto LABEL_11;
          }
          goto LABEL_82;
        }
        goto LABEL_38;
      }
      v14 = -1073741726;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_82;
      v23 = 24;
    }
    v24 = 3221225570LL;
    goto LABEL_81;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v17 = 21;
    goto LABEL_10;
  }
LABEL_82:
  GmsapFreeStringRoutine(0);
  GmsapFreeStringRoutine(v8);
  GmsapFreeStringRoutine(0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_70b8577d707437755865c965214ce19a_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x18000461c  mov     [rsp-38h+arg_8], rbx
0x180004621  mov     [rsp-38h+arg_18], r9
0x180004626  push    rbp
0x180004627  push    rsi
0x180004628  push    rdi
0x180004629  push    r12
0x18000462b  push    r13
0x18000462d  push    r14
0x18000462f  push    r15
0x180004631  mov     rbp, rsp
0x180004634  sub     rsp, 50h
0x180004638  xor     r13d, r13d
0x18000463b  xorps   xmm0, xmm0
0x18000463e  xorps   xmm1, xmm1
0x180004641  mov     [rbp+Str], r13
0x180004645  movups  xmmword ptr [rbp+SourceString.Length], xmm0
0x180004649  mov     edi, r13d
0x18000464c  mov     r12d, r13d
0x18000464f  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x180004653  mov     [rbp+hMem], r13
0x180004657  mov     r15, r9
0x18000465a  mov     r14, r8
0x18000465d  mov     rsi, rdx
0x180004660  mov     rbx, rcx
0x180004663  mov     rcx, cs:WPP_GLOBAL_Control
0x18000466a  lea     rax, WPP_GLOBAL_Control
0x180004671  cmp     rcx, rax
0x180004674  jz      short loc_180004690
0x180004676  test    byte ptr [rcx+1Ch], 8
0x18000467a  jz      short loc_180004690
0x18000467c  mov     rcx, [rcx+10h]
0x180004680  lea     edx, [r13+13h]
0x180004684  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x18000468b  call    WPP_SF_
0x180004690  mov     rax, [rbp+arg_20]
0x180004694  mov     rdx, [rbp+arg_28]
0x180004698  mov     rcx, [rbp+arg_30]
0x18000469c  mov     [r15], r13
0x18000469f  mov     [rax], r13
0x1800046a2  mov     [rdx], r13
0x1800046a5  mov     dword ptr [rcx], 1
0x1800046ab  test    rbx, rbx
0x1800046ae  jz      short loc_1800046D0
0x1800046b0  mov     rax, [rbx+10h]
0x1800046b4  mov     [r15], rax
0x1800046b7  mov     rax, [rbx+18h]
0x1800046bb  mov     ebx, r13d
0x1800046be  mov     [rdx], rax
0x1800046c1  mov     [rcx], r13d
0x1800046c4  lea     rsi, WPP_GLOBAL_Control
0x1800046cb  jmp     loc_180004B58
0x1800046d0  lea     rdx, [rbp+Str]
0x1800046d4  mov     rcx, rsi; SourceString
0x1800046d7  call    GmsapDuplicateWStr
0x1800046dc  mov     ebx, eax
0x1800046de  test    eax, eax
0x1800046e0  jns     short loc_18000471C
0x1800046e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046e9  lea     rsi, WPP_GLOBAL_Control
0x1800046f0  cmp     rcx, rsi
0x1800046f3  jz      short loc_180004713
0x1800046f5  test    byte ptr [rcx+1Ch], 4
0x1800046f9  jz      short loc_180004713
0x1800046fb  mov     edx, 14h
0x180004700  mov     r9d, eax
0x180004703  mov     rcx, [rcx+10h]
0x180004707  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x18000470e  call    WPP_SF_D
0x180004713  mov     rdi, [rbp+Str]
0x180004717  jmp     loc_180004B58
0x18000471c  lea     rdx, [rbp+hMem]
0x180004720  mov     rcx, r14; SourceString
0x180004723  call    GmsapDuplicateWStr
0x180004728  mov     ebx, eax
0x18000472a  test    eax, eax
0x18000472c  jns     short loc_18000474E
0x18000472e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004735  lea     rsi, WPP_GLOBAL_Control
0x18000473c  cmp     rcx, rsi
0x18000473f  jz      short loc_180004713
0x180004741  test    byte ptr [rcx+1Ch], 4
0x180004745  jz      short loc_180004713
0x180004747  mov     edx, 15h
0x18000474c  jmp     short loc_180004700
0x18000474e  mov     rdi, [rbp+Str]
0x180004752  mov     edx, 40h ; '@'; Ch
0x180004757  mov     rcx, rdi; Str
0x18000475a  call    cs:__imp_wcsrchr
0x180004761  nop     dword ptr [rax+rax+00h]
0x180004766  test    rax, rax
0x180004769  jz      loc_18000481E
0x18000476f  lea     rbx, [rax+2]
0x180004773  mov     [rax], r13w
0x180004777  cmp     r13w, [rbx]
0x18000477b  jz      short loc_1800047E8
0x18000477d  cmp     r13w, [rdi]
0x180004781  jz      short loc_1800047E8
0x180004783  mov     rcx, [rbp+hMem]; hMem
0x180004787  call    GmsapFreeStringRoutine
0x18000478c  mov     rdx, rbx; SourceString
0x18000478f  mov     [rbp+hMem], r13
0x180004793  lea     rcx, [rbp+DestinationString]; DestinationString
0x180004797  call    cs:__imp_RtlInitUnicodeString
0x18000479e  nop     dword ptr [rax+rax+00h]
0x1800047a3  lea     rdx, [rbp+hMem]
0x1800047a7  lea     rcx, [rbp+DestinationString]; SourceString
0x1800047ab  call    GmsapDuplicateWStr
0x1800047b0  mov     ebx, eax
0x1800047b2  test    eax, eax
0x1800047b4  jns     loc_1800048E8
0x1800047ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047c1  lea     rsi, WPP_GLOBAL_Control
0x1800047c8  cmp     rcx, rsi
0x1800047cb  jz      loc_180004B58
0x1800047d1  test    byte ptr [rcx+1Ch], 4
0x1800047d5  jz      loc_180004B58
0x1800047db  mov     edx, 17h
0x1800047e0  mov     r9d, eax
0x1800047e3  jmp     loc_180004B48
0x1800047e8  mov     ebx, 0C0000062h
0x1800047ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047f4  lea     rsi, WPP_GLOBAL_Control
0x1800047fb  cmp     rcx, rsi
0x1800047fe  jz      loc_180004B58
0x180004804  test    byte ptr [rcx+1Ch], 4
0x180004808  jz      loc_180004B58
0x18000480e  mov     edx, 16h
0x180004813  mov     r9d, 0C0000062h
0x180004819  jmp     loc_180004B48
0x18000481e  mov     edx, 5Ch ; '\'; Ch
0x180004823  mov     rcx, rdi; Str
0x180004826  call    cs:__imp_wcsrchr
0x18000482d  nop     dword ptr [rax+rax+00h]
0x180004832  test    rax, rax
0x180004835  jz      loc_1800048E8
0x18000483b  mov     rcx, [rbp+hMem]; hMem
0x18000483f  lea     rbx, [rax+2]
0x180004843  mov     [rax], r13w
0x180004847  call    GmsapFreeStringRoutine
0x18000484c  mov     [rbp+hMem], rdi
0x180004850  mov     rdi, r13
0x180004853  mov     [rbp+Str], r13
0x180004857  cmp     r13w, [rbx]
0x18000485b  jnz     short loc_18000488A
0x18000485d  mov     ebx, 0C0000062h
0x180004862  mov     rcx, cs:WPP_GLOBAL_Control
0x180004869  lea     rsi, WPP_GLOBAL_Control
0x180004870  cmp     rcx, rsi
0x180004873  jz      loc_180004B58
0x180004879  test    byte ptr [rcx+1Ch], 4
0x18000487d  jz      loc_180004B58
0x180004883  mov     edx, 18h
0x180004888  jmp     short loc_180004813
0x18000488a  mov     rdx, rbx; SourceString
0x18000488d  lea     rcx, [rbp+SourceString]; DestinationString
0x180004891  call    cs:__imp_RtlInitUnicodeString
0x180004898  nop     dword ptr [rax+rax+00h]
0x18000489d  lea     rdx, [rbp+Str]
0x1800048a1  lea     rcx, [rbp+SourceString]; SourceString
0x1800048a5  call    GmsapDuplicateWStr
0x1800048aa  test    eax, eax
0x1800048ac  jns     short loc_1800048E4
0x1800048ae  mov     ebx, 0C0000017h
0x1800048b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048ba  lea     rsi, WPP_GLOBAL_Control
0x1800048c1  cmp     rcx, rsi
0x1800048c4  jz      loc_180004713
0x1800048ca  test    byte ptr [rcx+1Ch], 4
0x1800048ce  jz      loc_180004713
0x1800048d4  mov     edx, 19h
0x1800048d9  mov     r9d, 0C0000017h
0x1800048df  jmp     loc_180004703
0x1800048e4  mov     rdi, [rbp+Str]
0x1800048e8  mov     rcx, [rbp+hMem]
0x1800048ec  test    rcx, rcx
0x1800048ef  jz      short loc_180004908
0x1800048f1  cmp     r13w, [rcx]
0x1800048f5  jz      short loc_180004908
0x1800048f7  mov     eax, 2Eh ; '.'
0x1800048fc  cmp     ax, [rcx]
0x1800048ff  jnz     short loc_180004952
0x180004901  cmp     r13w, [rcx+2]
0x180004906  jnz     short loc_180004952
0x180004908  lea     rdx, [rbp+hMem]
0x18000490c  lea     rcx, SourceString; SourceString
0x180004913  call    GmsapDuplicateWStr
0x180004918  test    eax, eax
0x18000491a  jns     short loc_180004952
0x18000491c  mov     ebx, 0C0000017h
0x180004921  mov     rcx, cs:WPP_GLOBAL_Control
0x180004928  lea     rsi, WPP_GLOBAL_Control
0x18000492f  cmp     rcx, rsi
0x180004932  jz      loc_180004B58
0x180004938  test    byte ptr [rcx+1Ch], 4
0x18000493c  jz      loc_180004B58
0x180004942  mov     edx, 1Ah
0x180004947  mov     r9d, 0C0000017h
0x18000494d  jmp     loc_180004B48
0x180004952  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004956  inc     rbx
0x180004959  cmp     [rdi+rbx*2], r13w
0x18000495e  jnz     short loc_180004956
0x180004960  lea     r15d, [rbx-1]
0x180004964  mov     eax, 24h ; '$'
0x180004969  cmp     ax, [rdi+r15*2]
0x18000496e  jnz     short loc_180004979
0x180004970  mov     r14d, ebx
0x180004973  lea     r13d, [rax-23h]
0x180004977  jmp     short loc_180004987
0x180004979  lea     r14d, [rbx+2]
0x18000497d  cmp     r14d, 2
0x180004981  jb      loc_180004B1F
0x180004987  mov     esi, r14d
0x18000498a  mov     edx, 0FFFFFFFFh
0x18000498f  lea     rax, [rsi+rsi]
0x180004993  cmp     rax, rdx
0x180004996  ja      loc_180004AFA
0x18000499c  mov     edx, eax; uBytes
0x18000499e  mov     ecx, 40h ; '@'; uFlags
0x1800049a3  call    cs:__imp_LocalAlloc
0x1800049aa  nop     dword ptr [rax+rax+00h]
0x1800049af  xor     r8d, r8d
0x1800049b2  mov     r12, rax
0x1800049b5  test    rax, rax
0x1800049b8  jnz     short loc_1800049C4
0x1800049ba  mov     ebx, 0C0000017h
0x1800049bf  jmp     loc_1800046C4
0x1800049c4  cmp     r14d, ebx
0x1800049c7  jnz     loc_180004A8B
0x1800049cd  test    r14d, r14d
0x1800049d0  jz      short loc_180004A4F
0x1800049d2  cmp     rsi, 7FFFFFFFh
0x1800049d9  jbe     short loc_1800049E2
0x1800049db  mov     ebx, 0C000000Dh
0x1800049e0  jmp     short loc_180004A59
0x1800049e2  cmp     r15, 7FFFFFFEh
0x1800049e9  ja      short loc_1800049DB
0x1800049eb  mov     rax, rdi
0x1800049ee  mov     rdx, r12
0x1800049f1  test    r15, r15
0x1800049f4  jz      short loc_180004A12
0x1800049f6  movzx   ecx, word ptr [rax]
0x1800049f9  test    cx, cx
0x1800049fc  jz      short loc_180004A12
0x1800049fe  mov     [rdx], cx
0x180004a01  add     rax, 2
0x180004a05  add     rdx, 2
0x180004a09  dec     r15
0x180004a0c  sub     rsi, 1
0x180004a10  jnz     short loc_1800049F1
0x180004a12  mov     rax, rsi
0x180004a15  lea     rcx, [rdx-2]
0x180004a19  neg     rax
0x180004a1c  sbb     ebx, ebx
0x180004a1e  not     ebx
0x180004a20  and     ebx, 80000005h
0x180004a26  test    rsi, rsi
0x180004a29  cmovnz  rcx, rdx
0x180004a2d  mov     [rcx], r8w
0x180004a31  jz      short loc_180004A5D
0x180004a33  mov     rax, [rbp+arg_18]
0x180004a37  test    r13d, r13d
0x180004a3a  jz      loc_180004AD3
0x180004a40  mov     [rax], r12
0x180004a43  mov     rax, [rbp+arg_20]
0x180004a47  mov     [rax], rdi
0x180004a4a  jmp     loc_180004ADD
0x180004a4f  mov     ebx, 0C000000Dh
0x180004a54  test    r14d, r14d
0x180004a57  jz      short loc_180004A5D
0x180004a59  mov     [rax], r8w
0x180004a5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a64  lea     rsi, WPP_GLOBAL_Control
0x180004a6b  cmp     rcx, rsi
0x180004a6e  jz      loc_180004B58
0x180004a74  test    byte ptr [rcx+1Ch], 4
0x180004a78  jz      loc_180004B58
0x180004a7e  mov     edx, 1Dh
0x180004a83  mov     r9d, ebx
0x180004a86  jmp     loc_180004B48
0x180004a8b  mov     r9, rdi
0x180004a8e  lea     r8, aWs; "%ws$"
0x180004a95  mov     rdx, rsi; unsigned __int64
0x180004a98  mov     rcx, r12; unsigned __int16 *
0x180004a9b  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004aa0  xor     r8d, r8d
0x180004aa3  mov     ebx, eax
0x180004aa5  test    eax, eax
0x180004aa7  jns     short loc_180004A33
0x180004aa9  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ab0  lea     rsi, WPP_GLOBAL_Control
0x180004ab7  cmp     rcx, rsi
0x180004aba  jz      loc_180004B58
0x180004ac0  test    byte ptr [rcx+1Ch], 4
0x180004ac4  jz      loc_180004B58
0x180004aca  lea     edx, [r8+1Eh]
0x180004ace  jmp     loc_1800047E0
0x180004ad3  mov     [rax], rdi
0x180004ad6  mov     rax, [rbp+arg_20]
0x180004ada  mov     [rax], r12
  ... truncated ...
```
