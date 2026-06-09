# CMediaServerCollectionChangeListener::Invoke(Windows::Media::Streaming::IBasicDevice *,Windows::Media::Streaming::ConnectionStatus)

- ea: `0x180008fb0`
- end: `0x1800092b0`
- name: `?Invoke@CMediaServerCollectionChangeListener@@UEAAJPEAUIBasicDevice@Streaming@Media@Windows@@W4ConnectionStatus@345@@Z`
- size: `768`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180002c00`
- `0x1800030b0`
- `0x180007b44`
- `0x180008fb0`
- `0x18000c84c`
- `0x1800198d4`
- `0x180019958`
- `0x18001e6f4`
- `0x180025030`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008fde`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008fde`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009278`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009278`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009098`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800090f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009146`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009098`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800090f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009146`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000925d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000926e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000925d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000926e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMediaServerCollectionChangeListener::Invoke(
        __int64 a1,
        struct Windows::Media::Streaming::IBasicDevice *a2,
        int a3)
{
  struct Windows::Media::Streaming::IBasicDevice *v4; // r14
  __int64 v5; // rdi
  struct _RTL_CRITICAL_SECTION *v6; // r15
  int v7; // ebx
  int v8; // r12d
  PCWSTR StringRawBuffer; // rax
  unsigned int v10; // eax
  PCWSTR v11; // rax
  __int64 v12; // rdx
  int v13; // r8d
  __int64 v14; // r11
  unsigned int v15; // ecx
  WCHAR v16; // ax
  __int64 v17; // r9
  __int64 *i; // rax
  int v19; // r9d
  _DWORD v21[14]; // [rsp+0h] [rbp-98h] BYREF
  HSTRING string; // [rsp+38h] [rbp-60h] BYREF
  HSTRING v23; // [rsp+40h] [rbp-58h] BYREF
  PCWSTR v24; // [rsp+48h] [rbp-50h]
  struct _RTL_CRITICAL_SECTION *v25; // [rsp+50h] [rbp-48h]
  char v26; // [rsp+58h] [rbp-40h]
  int v29; // [rsp+B8h] [rbp+20h]

  v4 = a2;
  v5 = a1;
  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 96);
  v25 = (struct _RTL_CRITICAL_SECTION *)(a1 + 96);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
  v26 = 1;
  v7 = 0;
  v8 = 0;
  v29 = 0;
  string = 0;
  v23 = 0;
  if ( !*(_DWORD *)(v5 + 240) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_843f9b73b5843d1b8d7c57834cd63f0f_Traceguids, v5);
    }
    goto LABEL_45;
  }
  (*(void (__fastcall **)(struct Windows::Media::Streaming::IBasicDevice *, HSTRING *))(*(_QWORD *)v4 + 48LL))(
    v4,
    &string);
  if ( (a3 & 0xFFFFFFFD) != 0 )
  {
    if ( a3 != 1 )
      goto LABEL_19;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        &WPP_843f9b73b5843d1b8d7c57834cd63f0f_Traceguids,
        StringRawBuffer);
    }
    v8 = 16;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v10 = (unsigned int)WindowsGetStringRawBuffer(string, 0);
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        (unsigned int)&WPP_843f9b73b5843d1b8d7c57834cd63f0f_Traceguids,
        v10,
        a3);
    }
    v8 = 8;
  }
  v29 = v8;
LABEL_19:
  (*(void (__fastcall **)(struct Windows::Media::Streaming::IBasicDevice *, HSTRING *))(*(_QWORD *)v4 + 80LL))(v4, &v23);
  v11 = WindowsGetStringRawBuffer(v23, 0);
  v14 = (__int64)v11;
  v24 = v11;
  try
  {
    if ( !v11 )
      ATL::AtlThrowImpl(-2147467259);
    v15 = 0;
    v16 = *v11;
    if ( v16 )
    {
      v12 = v14;
      do
      {
        v15 = v16 + 33 * v15;
        v12 += 2;
        v16 = *(_WORD *)v12;
      }
      while ( *(_WORD *)v12 );
    }
    v17 = *(_QWORD *)(v5 + 136);
    if ( v17 )
    {
      v12 = v15 % *(_DWORD *)(v5 + 152);
      for ( i = *(__int64 **)(v17 + 8 * v12); i; i = (__int64 *)i[2] )
      {
        if ( *((_DWORD *)i + 6) == v15 )
        {
          v12 = *i;
          do
          {
            v13 = *(unsigned __int16 *)(v12 + v14 - *i);
            v19 = *(unsigned __int16 *)v12 - v13;
            if ( v19 )
              break;
            v12 += 2;
          }
          while ( v13 );
          if ( !v19 )
            goto LABEL_35;
        }
      }
    }
    i = 0;
LABEL_35:
    if ( i )
      *(_DWORD *)(i[1] + 16) = a3;
    else
      v7 = -2147467259;
  }
  catch ( ... )
  {
    v12 = (__int64)v21;
    v21[12] = -2147024882;
    v5 = a1;
    v4 = a2;
    v7 = -2147024882;
    v8 = v29;
    v6 = v25;
    v14 = (__int64)v24;
    goto LABEL_41;
  }
  if ( v7 < 0 )
  {
LABEL_41:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_qS(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, v5, v14);
    }
  }
  else if ( v8 )
  {
    CMediaServerCollectionChangeListener::AddClientRef((CMediaServerCollectionChangeListener *)v5);
  }
LABEL_45:
  if ( v23 )
    WindowsDeleteString(v23);
  if ( string )
    WindowsDeleteString(string);
  LeaveCriticalSection(v6);
  if ( v7 >= 0 && v8 )
  {
    CMediaServerCollectionChangeListener::NotifyListQueue::Queue(
      (CMediaServerCollectionChangeListener::NotifyListQueue *)(v5 + 48),
      v4,
      v8);
    CMediaServerCollectionChangeListener::ReleaseClientRef((CMediaServerCollectionChangeListener *)v5);
  }
  return 0;
}

```

## disassembly

```asm
0x180008fb0  mov     [rsp+arg_8], rdx
0x180008fb5  mov     [rsp+arg_0], rcx
0x180008fba  push    rbx
0x180008fbb  push    rsi
0x180008fbc  push    rdi
0x180008fbd  push    r12
0x180008fbf  push    r13
0x180008fc1  push    r14
0x180008fc3  push    r15
0x180008fc5  sub     rsp, 60h
0x180008fc9  mov     esi, r8d
0x180008fcc  mov     r14, rdx
0x180008fcf  mov     rdi, rcx
0x180008fd2  lea     r15, [rcx+60h]
0x180008fd6  mov     [rsp+98h+var_48], r15
0x180008fdb  mov     rcx, r15; lpCriticalSection
0x180008fde  call    cs:__imp_EnterCriticalSection
0x180008fe4  mov     [rsp+98h+var_40], 1
0x180008fe9  xor     eax, eax
0x180008feb  mov     ebx, eax
0x180008fed  mov     r12d, eax
0x180008ff0  mov     [rsp+98h+arg_18], eax
0x180008ff7  mov     [rsp+98h+string], rax
0x180008ffc  mov     [rsp+98h+var_58], rax
0x180009001  cmp     [rdi+0F0h], eax
0x180009007  jnz     short loc_180009051
0x180009009  lea     r13, WPP_GLOBAL_Control
0x180009010  mov     rcx, cs:WPP_GLOBAL_Control
0x180009017  cmp     rcx, r13
0x18000901a  jz      loc_180009253
0x180009020  test    byte ptr [rcx+1Ch], 40h
0x180009024  jz      loc_180009253
0x18000902a  cmp     byte ptr [rcx+19h], 4
0x18000902e  jb      loc_180009253
0x180009034  mov     edx, 14h
0x180009039  mov     r9, rdi
0x18000903c  lea     r8, WPP_843f9b73b5843d1b8d7c57834cd63f0f_Traceguids
0x180009043  mov     rcx, [rcx+10h]
0x180009047  call    WPP_SF_q
0x18000904c  jmp     loc_180009253
0x180009051  mov     rax, [r14]
0x180009054  lea     rdx, [rsp+98h+string]
0x180009059  mov     rcx, r14
0x18000905c  mov     rax, [rax+30h]
0x180009060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009065  test    esi, 0FFFFFFFDh
0x18000906b  jz      short loc_1800090CE
0x18000906d  cmp     esi, 1
0x180009070  jnz     short loc_1800090C5
0x180009072  lea     r13, WPP_GLOBAL_Control
0x180009079  mov     rax, cs:WPP_GLOBAL_Control
0x180009080  cmp     rax, r13
0x180009083  jz      short loc_1800090BD
0x180009085  test    byte ptr [rax+1Ch], 40h
0x180009089  jz      short loc_1800090BD
0x18000908b  cmp     byte ptr [rax+19h], 4
0x18000908f  jb      short loc_1800090BD
0x180009091  xor     edx, edx; length
0x180009093  mov     rcx, [rsp+98h+string]; string
0x180009098  call    cs:__imp_WindowsGetStringRawBuffer
0x18000909e  mov     edx, 16h
0x1800090a3  mov     r9, rax
0x1800090a6  lea     r8, WPP_843f9b73b5843d1b8d7c57834cd63f0f_Traceguids
0x1800090ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090b4  mov     rcx, [rcx+10h]
0x1800090b8  call    WPP_SF_S
0x1800090bd  mov     r12d, 10h
0x1800090c3  jmp     short loc_180009123
0x1800090c5  lea     r13, WPP_GLOBAL_Control
0x1800090cc  jmp     short loc_18000912B
0x1800090ce  lea     r13, WPP_GLOBAL_Control
0x1800090d5  mov     rax, cs:WPP_GLOBAL_Control
0x1800090dc  cmp     rax, r13
0x1800090df  jz      short loc_18000911D
0x1800090e1  test    byte ptr [rax+1Ch], 40h
0x1800090e5  jz      short loc_18000911D
0x1800090e7  cmp     byte ptr [rax+19h], 4
0x1800090eb  jb      short loc_18000911D
0x1800090ed  xor     edx, edx; length
0x1800090ef  mov     rcx, [rsp+98h+string]; string
0x1800090f4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800090fa  mov     edx, 15h
0x1800090ff  mov     dword ptr [rsp+98h+var_78], esi
0x180009103  mov     r9, rax
0x180009106  lea     r8, WPP_843f9b73b5843d1b8d7c57834cd63f0f_Traceguids
0x18000910d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009114  mov     rcx, [rcx+10h]
0x180009118  call    WPP_SF_Sd
0x18000911d  mov     r12d, 8
0x180009123  mov     [rsp+98h+arg_18], r12d
0x18000912b  mov     rax, [r14]
0x18000912e  lea     rdx, [rsp+98h+var_58]
0x180009133  mov     rcx, r14
0x180009136  mov     rax, [rax+50h]
0x18000913a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000913f  xor     edx, edx; length
0x180009141  mov     rcx, [rsp+98h+var_58]; string
0x180009146  call    cs:__imp_WindowsGetStringRawBuffer
0x18000914c  mov     r11, rax
0x18000914f  mov     [rsp+98h+var_50], rax
0x180009154  test    rax, rax
0x180009157  jnz     short loc_180009164
0x180009159  mov     ecx, 80004005h; int
0x18000915e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009164  xor     ecx, ecx
0x180009166  movzx   eax, word ptr [rax]
0x180009169  test    ax, ax
0x18000916c  jz      short loc_180009185
0x18000916e  mov     rdx, r11
0x180009171  imul    ecx, 21h ; '!'
0x180009174  movzx   eax, ax
0x180009177  add     ecx, eax
0x180009179  lea     rdx, [rdx+2]
0x18000917d  movzx   eax, word ptr [rdx]
0x180009180  test    ax, ax
0x180009183  jnz     short loc_180009171
0x180009185  mov     r9, [rdi+88h]
0x18000918c  test    r9, r9
0x18000918f  jz      short loc_1800091D4
0x180009191  xor     edx, edx
0x180009193  mov     eax, ecx
0x180009195  div     dword ptr [rdi+98h]
0x18000919b  mov     rax, [r9+rdx*8]
0x18000919f  test    rax, rax
0x1800091a2  jz      short loc_1800091D4
0x1800091a4  cmp     [rax+18h], ecx
0x1800091a7  jnz     short loc_1800091CE
0x1800091a9  mov     rdx, [rax]
0x1800091ac  mov     r10, r11
0x1800091af  sub     r10, rdx
0x1800091b2  movzx   r9d, word ptr [rdx]
0x1800091b6  movzx   r8d, word ptr [rdx+r10]
0x1800091bb  sub     r9d, r8d
0x1800091be  jnz     short loc_1800091C9
0x1800091c0  add     rdx, 2
0x1800091c4  test    r8d, r8d
0x1800091c7  jnz     short loc_1800091B2
0x1800091c9  test    r9d, r9d
0x1800091cc  jz      short loc_1800091D6
0x1800091ce  mov     rax, [rax+10h]
0x1800091d2  jmp     short loc_18000919F
0x1800091d4  xor     eax, eax
0x1800091d6  test    rax, rax
0x1800091d9  jz      short loc_1800091E4
0x1800091db  mov     rax, [rax+8]
0x1800091df  mov     [rax+10h], esi
0x1800091e2  jmp     short loc_1800091E9
0x1800091e4  mov     ebx, 80004005h
0x1800091e9  test    ebx, ebx
0x1800091eb  js      short loc_180009229
0x1800091ed  test    r12d, r12d
0x1800091f0  jz      short loc_180009253
0x1800091f2  mov     rcx, rdi; this
0x1800091f5  call    ?AddClientRef@CMediaServerCollectionChangeListener@@QEAAXXZ; CMediaServerCollectionChangeListener::AddClientRef(void)
0x1800091fa  jmp     short loc_180009253
0x1800091fc  lea     r13, WPP_GLOBAL_Control
0x180009203  mov     rdi, [rsp+98h+arg_0]
0x18000920b  mov     r14, [rsp+98h+arg_8]
0x180009213  mov     ebx, [rsp+98h+var_68]
0x180009217  mov     r12d, [rsp+98h+arg_18]
0x18000921f  mov     r15, [rsp+98h+var_48]
0x180009224  mov     r11, [rsp+98h+var_50]
0x180009229  mov     rcx, cs:WPP_GLOBAL_Control
0x180009230  cmp     rcx, r13
0x180009233  jz      short loc_180009253
0x180009235  test    byte ptr [rcx+1Ch], 40h
0x180009239  jz      short loc_180009253
0x18000923b  cmp     byte ptr [rcx+19h], 4
0x18000923f  jb      short loc_180009253
0x180009241  mov     [rsp+98h+var_78], r11
0x180009246  mov     r9, rdi
0x180009249  mov     rcx, [rcx+10h]
0x18000924d  call    WPP_SF_qS
0x180009252  nop
0x180009253  mov     rcx, [rsp+98h+var_58]; string
0x180009258  test    rcx, rcx
0x18000925b  jz      short loc_180009264
0x18000925d  call    cs:__imp_WindowsDeleteString
0x180009263  nop
0x180009264  mov     rcx, [rsp+98h+string]; string
0x180009269  test    rcx, rcx
0x18000926c  jz      short loc_180009275
0x18000926e  call    cs:__imp_WindowsDeleteString
0x180009274  nop
0x180009275  mov     rcx, r15; lpCriticalSection
0x180009278  call    cs:__imp_LeaveCriticalSection
0x18000927e  test    ebx, ebx
0x180009280  js      short loc_18000929E
0x180009282  test    r12d, r12d
0x180009285  jz      short loc_18000929E
0x180009287  lea     rcx, [rdi+30h]; this
0x18000928b  mov     r8d, r12d; int
0x18000928e  mov     rdx, r14; struct Windows::Media::Streaming::IBasicDevice *
0x180009291  call    ?Queue@NotifyListQueue@CMediaServerCollectionChangeListener@@QEAAJPEAUIBasicDevice@Streaming@Media@Windows@@J@Z; CMediaServerCollectionChangeListener::NotifyListQueue::Queue(Windows::Media::Streaming::IBasicDevice *,long)
0x180009296  mov     rcx, rdi; this
0x180009299  call    ?ReleaseClientRef@CMediaServerCollectionChangeListener@@QEAAXXZ; CMediaServerCollectionChangeListener::ReleaseClientRef(void)
0x18000929e  xor     eax, eax
0x1800092a0  add     rsp, 60h
0x1800092a4  pop     r15
0x1800092a6  pop     r14
0x1800092a8  pop     r13
0x1800092aa  pop     r12
0x1800092ac  pop     rdi
0x1800092ad  pop     rsi
0x1800092ae  pop     rbx
0x1800092af  retn
```
