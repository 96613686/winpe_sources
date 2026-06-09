# CRedbookTracks::AddTrack(ulong)

- ea: `0x180015260`
- end: `0x18001549c`
- name: `?AddTrack@CRedbookTracks@@QEAAJK@Z`
- size: `572`
- prototype: `__int64 __fastcall(CRedbookTracks *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000a430`

## callees

- `0x180001144`
- `0x18000115c`
- `0x180015260`
- `0x180016bc0`
- `0x180016dc4`
- `0x180016e50`
- `0x180018500`
- `0x180019010`

## import_xrefs

- `SHLWAPI!SHCreateStreamOnFileEx` at `0x18001531e`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x1800153db`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x18001531e`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x1800153db`

## pseudocode

```c
__int64 __fastcall CRedbookTracks::AddTrack(CRedbookTracks *this, unsigned int a2)
{
  int v2; // ebx
  const unsigned __int16 *v5; // r8
  HRESULT v6; // esi
  _QWORD *v7; // rax
  _QWORD *v8; // r14
  _QWORD *v9; // r15
  int v10; // edx
  int v11; // r8d
  const WCHAR *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r8
  IStream *pstmTemplate; // [rsp+20h] [rbp-278h]
  IStream *ppstm; // [rsp+30h] [rbp-268h] BYREF
  WCHAR pszFile[272]; // [rsp+40h] [rbp-258h] BYREF

  v2 = *((_DWORD *)this + 4);
  if ( v2 >= 99 )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    while ( 1 )
    {
      v5 = L"%s:t%02x";
      if ( !*((_DWORD *)this + 8) )
        v5 = L"%s_t%02x";
      LODWORD(pstmTemplate) = v2;
      v6 = StringCbPrintfW(pszFile, 0x218u, v5, *((_QWORD *)this + 5), pstmTemplate);
      if ( v6 < 0 )
        break;
      v7 = operator new(0x18u);
      v8 = v7;
      if ( !v7 )
        return (unsigned int)-2147467259;
      v9 = v7 + 1;
      *(_OWORD *)v7 = 0;
      v7[2] = 0;
      *((_DWORD *)v7 + 4) = a2;
      v6 = SHCreateStreamOnFileEx(pszFile, 0x1012u, 0x4000100u, 0, 0, (IStream **)v7 + 1);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 7), v10, v11, v6, (__int64)pszFile);
      if ( v6 >= 0 )
      {
        if ( *((_DWORD *)this + 8) )
        {
          if ( !v2 )
          {
            v12 = (const WCHAR *)*((_QWORD *)this + 5);
            ppstm = 0;
            SHCreateStreamOnFileEx(v12, 0x1012u, 0x4000100u, 0, 0, &ppstm);
            if ( ppstm )
              (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
          }
        }
        if ( a2 <= 0x12C )
          a2 = 300;
        v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v9 + 48LL))(*v9, 2352 * a2);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_di(*((_QWORD *)WPP_GLOBAL_Control + 7), v13, v14, (unsigned int)v6, 2352 * a2);
        if ( v6 >= 0 )
        {
          *v8 = 0;
          if ( *(_QWORD *)this )
            **((_QWORD **)this + 1) = v8;
          else
            *(_QWORD *)this = v8;
          *((_QWORD *)this + 1) = v8;
          ++*((_DWORD *)this + 4);
          return (unsigned int)v6;
        }
LABEL_14:
        if ( *v9 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 16LL))(*v9);
          *v9 = 0;
        }
        operator delete(v8);
        return (unsigned int)v6;
      }
      if ( !*((_DWORD *)this + 8) )
        goto LABEL_14;
      *((_DWORD *)this + 8) = 0;
      if ( *v9 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 16LL))(*v9);
        *v9 = 0;
      }
      operator delete(v8);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180015260  mov     [rsp+arg_10], rbx
0x180015265  mov     [rsp+arg_18], rbp
0x18001526a  push    rsi
0x18001526b  push    rdi
0x18001526c  push    r12
0x18001526e  push    r14
0x180015270  push    r15
0x180015272  sub     rsp, 270h
0x180015279  mov     rax, cs:__security_cookie
0x180015280  xor     rax, rsp
0x180015283  mov     [rsp+298h+var_38], rax
0x18001528b  mov     ebx, [rcx+10h]
0x18001528e  mov     ebp, edx
0x180015290  mov     rdi, rcx
0x180015293  cmp     ebx, 63h ; 'c'
0x180015296  jge     loc_180015469
0x18001529c  xor     r12d, r12d
0x18001529f  cmp     [rdi+20h], r12d
0x1800152a3  lea     rax, aST02x_0; "%s_t%02x"
0x1800152aa  mov     r9, [rdi+28h]
0x1800152ae  lea     r8, aST02x; "%s:t%02x"
0x1800152b5  cmovz   r8, rax; unsigned __int16 *
0x1800152b9  mov     dword ptr [rsp+298h+pstmTemplate], ebx
0x1800152bd  mov     edx, 218h; unsigned __int64
0x1800152c2  lea     rcx, [rsp+298h+pszFile]; unsigned __int16 *
0x1800152c7  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800152cc  mov     esi, eax
0x1800152ce  test    eax, eax
0x1800152d0  js      loc_18001546E
0x1800152d6  mov     ecx, 18h; Size
0x1800152db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800152e0  mov     r14, rax
0x1800152e3  test    rax, rax
0x1800152e6  jz      loc_180015469
0x1800152ec  xorps   xmm0, xmm0
0x1800152ef  lea     r15, [r14+8]
0x1800152f3  movups  xmmword ptr [r14], xmm0
0x1800152f7  xor     eax, eax
0x1800152f9  mov     [rsp+298h+ppstm], r15; ppstm
0x1800152fe  mov     [r14+10h], rax
0x180015302  lea     rcx, [rsp+298h+pszFile]; pszFile
0x180015307  xor     r9d, r9d; fCreate
0x18001530a  mov     [r14+10h], ebp
0x18001530e  mov     edx, 1012h; grfMode
0x180015313  mov     [rsp+298h+pstmTemplate], r12; pstmTemplate
0x180015318  mov     r8d, 4000100h; dwAttributes
0x18001531e  call    cs:__imp_SHCreateStreamOnFileEx
0x180015324  mov     esi, eax
0x180015326  mov     rcx, cs:WPP_GLOBAL_Control
0x18001532d  lea     rax, WPP_GLOBAL_Control
0x180015334  cmp     rcx, rax
0x180015337  jz      short loc_180015355
0x180015339  test    byte ptr [rcx+44h], 1
0x18001533d  jz      short loc_180015355
0x18001533f  mov     rcx, [rcx+38h]
0x180015343  lea     rax, [rsp+298h+pszFile]
0x180015348  mov     r9d, esi
0x18001534b  mov     [rsp+298h+pstmTemplate], rax
0x180015350  call    WPP_SF_dS
0x180015355  test    esi, esi
0x180015357  jns     short loc_1800153AB
0x180015359  cmp     [rdi+20h], r12d
0x18001535d  jz      short loc_180015387
0x18001535f  mov     [rdi+20h], r12d
0x180015363  mov     rcx, [r15]
0x180015366  test    rcx, rcx
0x180015369  jz      short loc_18001537A
0x18001536b  mov     rax, [rcx]
0x18001536e  mov     rax, [rax+10h]
0x180015372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015377  mov     [r15], r12
0x18001537a  mov     rcx, r14; Block
0x18001537d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015382  jmp     loc_18001529F
0x180015387  mov     rcx, [r15]
0x18001538a  test    rcx, rcx
0x18001538d  jz      short loc_18001539E
0x18001538f  mov     rax, [rcx]
0x180015392  mov     rax, [rax+10h]
0x180015396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001539b  mov     [r15], r12
0x18001539e  mov     rcx, r14; Block
0x1800153a1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800153a6  jmp     loc_18001546E
0x1800153ab  cmp     [rdi+20h], r12d
0x1800153af  jz      short loc_1800153F7
0x1800153b1  test    ebx, ebx
0x1800153b3  jnz     short loc_1800153F7
0x1800153b5  mov     rcx, [rdi+28h]; pszFile
0x1800153b9  lea     rax, [rsp+298h+var_268]
0x1800153be  mov     [rsp+298h+ppstm], rax; ppstm
0x1800153c3  xor     r9d, r9d; fCreate
0x1800153c6  mov     edx, 1012h; grfMode
0x1800153cb  mov     [rsp+298h+pstmTemplate], r12; pstmTemplate
0x1800153d0  mov     r8d, 4000100h; dwAttributes
0x1800153d6  mov     [rsp+298h+var_268], r12
0x1800153db  call    cs:__imp_SHCreateStreamOnFileEx
0x1800153e1  mov     rcx, [rsp+298h+var_268]
0x1800153e6  test    rcx, rcx
0x1800153e9  jz      short loc_1800153F7
0x1800153eb  mov     rax, [rcx]
0x1800153ee  mov     rax, [rax+10h]
0x1800153f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153f7  mov     rcx, [r15]
0x1800153fa  mov     eax, 12Ch
0x1800153ff  cmp     ebp, eax
0x180015401  cmovbe  ebp, eax
0x180015404  mov     rax, [rcx]
0x180015407  imul    ebx, ebp, 930h
0x18001540d  mov     rax, [rax+30h]
0x180015411  mov     edx, ebx
0x180015413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015418  mov     esi, eax
0x18001541a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015421  lea     rax, WPP_GLOBAL_Control
0x180015428  cmp     rcx, rax
0x18001542b  jz      short loc_180015444
0x18001542d  test    byte ptr [rcx+44h], 1
0x180015431  jz      short loc_180015444
0x180015433  mov     rcx, [rcx+38h]
0x180015437  mov     r9d, esi
0x18001543a  mov     [rsp+298h+pstmTemplate], rbx
0x18001543f  call    WPP_SF_di
0x180015444  test    esi, esi
0x180015446  js      loc_180015387
0x18001544c  mov     [r14], r12
0x18001544f  cmp     [rdi], r12
0x180015452  jnz     short loc_180015459
0x180015454  mov     [rdi], r14
0x180015457  jmp     short loc_180015460
0x180015459  mov     rax, [rdi+8]
0x18001545d  mov     [rax], r14
0x180015460  mov     [rdi+8], r14
0x180015464  inc     dword ptr [rdi+10h]
0x180015467  jmp     short loc_18001546E
0x180015469  mov     esi, 80004005h
0x18001546e  mov     eax, esi
0x180015470  mov     rcx, [rsp+298h+var_38]
0x180015478  xor     rcx, rsp; StackCookie
0x18001547b  call    __security_check_cookie
0x180015480  lea     r11, [rsp+298h+var_28]
0x180015488  mov     rbx, [r11+40h]
0x18001548c  mov     rbp, [r11+48h]
0x180015490  mov     rsp, r11
0x180015493  pop     r15
0x180015495  pop     r14
0x180015497  pop     r12
0x180015499  pop     rdi
0x18001549a  pop     rsi
0x18001549b  retn
```
