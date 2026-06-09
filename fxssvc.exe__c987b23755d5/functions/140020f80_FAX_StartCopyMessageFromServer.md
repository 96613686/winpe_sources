# FAX_StartCopyMessageFromServer

- ea: `0x140020f80`
- end: `0x140021521`
- name: `FAX_StartCopyMessageFromServer`
- size: `1441`
- prototype: `unsigned int __fastcall(void *, struct _LIST_ENTRY *, unsigned int, struct _HANDLE_ENTRY **)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x140010150`
- `0x140012e20`
- `0x140020f80`
- `0x14002c92c`
- `0x140037b14`
- `0x140044f7c`
- `0x1400452ac`
- `0x140045798`
- `0x140065dbc`
- `0x14006a3a4`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400210b1`
- `KERNEL32!GetLastError` at `0x1400213a1`
- `KERNEL32!GetLastError` at `0x14002140f`
- `KERNEL32!GetLastError` at `0x1400214b6`
- `KERNEL32!GetLastError` at `0x1400210b1`
- `KERNEL32!GetLastError` at `0x1400213a1`
- `KERNEL32!GetLastError` at `0x14002140f`
- `KERNEL32!GetLastError` at `0x1400214b6`
- `KERNEL32!CloseHandle` at `0x1400214ac`
- `KERNEL32!CloseHandle` at `0x1400214ac`
- `KERNEL32!EnterCriticalSection` at `0x14002110f`
- `KERNEL32!EnterCriticalSection` at `0x14002147d`
- `KERNEL32!EnterCriticalSection` at `0x14002110f`
- `KERNEL32!EnterCriticalSection` at `0x14002147d`
- `KERNEL32!LeaveCriticalSection` at `0x14002113a`
- `KERNEL32!LeaveCriticalSection` at `0x14002119d`
- `KERNEL32!LeaveCriticalSection` at `0x140021202`
- `KERNEL32!LeaveCriticalSection` at `0x140021250`
- `KERNEL32!LeaveCriticalSection` at `0x14002149d`
- `KERNEL32!LeaveCriticalSection` at `0x14002113a`
- `KERNEL32!LeaveCriticalSection` at `0x14002119d`
- `KERNEL32!LeaveCriticalSection` at `0x140021202`
- `KERNEL32!LeaveCriticalSection` at `0x140021250`
- `KERNEL32!LeaveCriticalSection` at `0x14002149d`

## pseudocode

```c
unsigned int __fastcall FAX_StartCopyMessageFromServer(
        void *a1,
        struct _LIST_ENTRY *a2,
        unsigned int a3,
        struct _HANDLE_ENTRY **a4)
{
  struct _LIST_ENTRY *i; // rsi
  CMapDeviceId *v9; // rcx
  unsigned int result; // eax
  unsigned int v11; // edi
  void *ClientUserSID; // r15
  DWORD v13; // eax
  unsigned int PreviewFile; // ebx
  __int64 v15; // r14
  __int64 Flink_low; // r9
  struct _LIST_ENTRY *Blink; // rcx
  WCHAR *v18; // r8
  __int64 v19; // rax
  __int64 v20; // rdx
  WCHAR *v21; // rcx
  unsigned int v22; // edi
  unsigned int v23; // eax
  void *File; // rax
  DWORD LastError; // eax
  struct _HANDLE_ENTRY *NewCopyHandle; // rax
  DWORD v27; // eax
  DWORD v28; // eax
  unsigned int v29; // [rsp+40h] [rbp-278h] BYREF
  int v30[3]; // [rsp+44h] [rbp-274h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-268h] BYREF

  i = 0;
  v29 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 508, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v9 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 && *((_BYTE *)v9 + 25) >= 2u )
      WPP_SF_(*((_QWORD *)v9 + 2), 509, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
    return 87;
  }
  if ( a3 > 2 )
  {
    if ( v9 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 && *((_BYTE *)v9 + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)v9 + 2), 510, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, a3);
    return 87;
  }
  v30[0] = 0;
  result = FaxSvcAccessCheck(0x2000000u, v30, &v29, 1);
  if ( !result )
  {
    v11 = v29;
    if ( (v29 & 0xE03FF) == 0 )
      return 5;
    v29 = 0;
    if ( a3 == 2 )
    {
      ClientUserSID = GetClientUserSID();
      if ( ClientUserSID )
      {
        v15 = -1;
        EnterCriticalSection(&g_CsQueue);
        for ( i = g_QueueListHead.Flink; i != &g_QueueListHead; i = i->Flink )
        {
          if ( i[1].Flink == a2 )
          {
            if ( i )
            {
              if ( !AccessibleJob((struct _JOB_QUEUE *)i, 1, v11, ClientUserSID) )
              {
                LeaveCriticalSection(&g_CsQueue);
                PreviewFile = 7009;
                if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 513, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
                }
                goto LABEL_78;
              }
              PreviewFile = CreatePreviewFile((struct _JOB_QUEUE *)i);
              if ( PreviewFile )
              {
                LeaveCriticalSection(&g_CsQueue);
                if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    514,
                    &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                    PreviewFile);
                }
                goto LABEL_78;
              }
              LeaveCriticalSection(&g_CsQueue);
              Blink = i[37].Blink;
              v18 = FileName;
              v19 = 2147483646;
              v29 = 1;
              v20 = 260;
              do
              {
                if ( !v19 )
                  break;
                Flink_low = LOWORD(Blink->Flink);
                if ( !(_WORD)Flink_low )
                  break;
                *v18 = Flink_low;
                Blink = (struct _LIST_ENTRY *)((char *)Blink + 2);
                ++v18;
                --v19;
                --v20;
              }
              while ( v20 );
              v21 = v18 - 1;
              v22 = v20 == 0 ? 0x8007007A : 0;
              if ( v20 )
                v21 = v18;
              *v21 = 0;
              if ( !v20 )
              {
                if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    515,
                    &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                    v22);
                }
                PreviewFile = (unsigned __int16)v22;
                if ( (v22 & 0x1FFF0000) != 0x70000 )
                  PreviewFile = v22;
                goto LABEL_78;
              }
LABEL_66:
              File = (void *)InternalSafeCreateFile(FileName, 0x80000000, 1u, Flink_low, 3u, 128);
              v15 = (__int64)File;
              if ( File == (void *)-1LL )
              {
                LastError = GetLastError();
                PreviewFile = LastError;
                if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    517,
                    (unsigned int)&WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                    (unsigned int)FileName,
                    LastError);
                }
              }
              else
              {
                NewCopyHandle = CreateNewCopyHandle(a1, File, 0, 0, (struct _JOB_QUEUE *)i);
                if ( NewCopyHandle )
                {
                  *a4 = NewCopyHandle;
                }
                else
                {
                  v27 = GetLastError();
                  PreviewFile = v27;
                  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      518,
                      &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                      v27);
                  }
                }
              }
              if ( ClientUserSID )
LABEL_78:
                pMemFree(ClientUserSID);
              if ( PreviewFile )
              {
                if ( v29 )
                {
                  EnterCriticalSection(&g_CsQueue);
                  DecreaseJobRefCount((struct _JOB_QUEUE *)i, 1, 1, 1);
                  LeaveCriticalSection(&g_CsQueue);
                }
                if ( v15 != -1 )
                {
                  if ( CloseHandle((HANDLE)v15) )
                  {
                    v28 = GetLastError();
                    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        519,
                        &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                        v28);
                    }
                  }
                }
                goto LABEL_88;
              }
              goto LABEL_89;
            }
LABEL_30:
            LeaveCriticalSection(&g_CsQueue);
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 512, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
            }
            PreviewFile = 7009;
            goto LABEL_78;
          }
        }
        i = 0;
        goto LABEL_30;
      }
      v13 = GetLastError();
      PreviewFile = v13;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 511, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v13);
      }
      return PreviewFile;
    }
    v23 = FindArchivedMessageAfterAccessCheck(a3, a2, v11, 1, FileName);
    PreviewFile = v23;
    if ( !v23 )
    {
      ClientUserSID = 0;
      goto LABEL_66;
    }
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 516, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v23);
    }
LABEL_88:
    if ( PreviewFile != 8 )
    {
LABEL_89:
      if ( PreviewFile != 14 )
        return PreviewFile;
    }
    return 7001;
  }
  return result;
}

```

## disassembly

```asm
0x140020f80  push    rbx
0x140020f82  push    rbp
0x140020f83  push    rsi
0x140020f84  push    rdi
0x140020f85  push    r12
0x140020f87  push    r13
0x140020f89  push    r14
0x140020f8b  push    r15
0x140020f8d  sub     rsp, 278h
0x140020f94  mov     rax, cs:__security_cookie
0x140020f9b  xor     rax, rsp
0x140020f9e  mov     [rsp+2B8h+var_58], rax
0x140020fa6  xor     esi, esi
0x140020fa8  mov     r12, r9
0x140020fab  mov     [rsp+2B8h+var_278], esi
0x140020faf  mov     ebx, r8d
0x140020fb2  mov     rbp, rdx
0x140020fb5  mov     r13, rcx
0x140020fb8  mov     rcx, cs:WPP_GLOBAL_Control
0x140020fbf  lea     r15, WPP_GLOBAL_Control
0x140020fc6  mov     r14b, 4
0x140020fc9  cmp     rcx, r15
0x140020fcc  jz      short loc_140020FF6
0x140020fce  test    [rcx+1Ch], r14b
0x140020fd2  jz      short loc_140020FF6
0x140020fd4  cmp     byte ptr [rcx+19h], 5
0x140020fd8  jb      short loc_140020FF6
0x140020fda  mov     rcx, [rcx+10h]
0x140020fde  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140020fe5  mov     edx, 1FCh
0x140020fea  call    WPP_SF_
0x140020fef  mov     rcx, cs:WPP_GLOBAL_Control
0x140020ff6  test    rbp, rbp
0x140020ff9  jnz     short loc_140021023
0x140020ffb  cmp     rcx, r15
0x140020ffe  jz      short loc_140021051
0x140021000  test    [rcx+1Ch], r14b
0x140021004  jz      short loc_140021051
0x140021006  cmp     byte ptr [rcx+19h], 2
0x14002100a  jb      short loc_140021051
0x14002100c  mov     rcx, [rcx+10h]
0x140021010  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140021017  mov     edx, 1FDh
0x14002101c  call    WPP_SF_
0x140021021  jmp     short loc_140021051
0x140021023  cmp     ebx, 2
0x140021026  jbe     short loc_14002105B
0x140021028  cmp     rcx, r15
0x14002102b  jz      short loc_140021051
0x14002102d  test    [rcx+1Ch], r14b
0x140021031  jz      short loc_140021051
0x140021033  cmp     byte ptr [rcx+19h], 2
0x140021037  jb      short loc_140021051
0x140021039  mov     rcx, [rcx+10h]
0x14002103d  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140021044  mov     edx, 1FEh
0x140021049  mov     r9d, ebx
0x14002104c  call    WPP_SF_d
0x140021051  mov     eax, 57h ; 'W'
0x140021056  jmp     loc_1400214FD
0x14002105b  mov     r9d, 1; int
0x140021061  mov     [rsp+2B8h+var_274], esi
0x140021065  lea     r8, [rsp+2B8h+var_278]; unsigned int *
0x14002106a  mov     ecx, 2000000h; unsigned int
0x14002106f  lea     rdx, [rsp+2B8h+var_274]; int *
0x140021074  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x140021079  test    eax, eax
0x14002107b  jnz     loc_1400214FD
0x140021081  mov     edi, [rsp+2B8h+var_278]
0x140021085  test    edi, 0E03FFh
0x14002108b  jnz     short loc_140021097
0x14002108d  mov     eax, 5
0x140021092  jmp     loc_1400214FD
0x140021097  mov     [rsp+2B8h+var_278], esi
0x14002109b  cmp     ebx, 2
0x14002109e  jnz     loc_14002130A
0x1400210a4  call    ?GetClientUserSID@@YAPEAXXZ; GetClientUserSID(void)
0x1400210a9  mov     r15, rax
0x1400210ac  test    rax, rax
0x1400210af  jnz     short loc_140021101
0x1400210b1  call    cs:__imp_GetLastError
0x1400210b7  mov     ebx, eax
0x1400210b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400210c0  lea     r12, WPP_GLOBAL_Control
0x1400210c7  cmp     rcx, r12
0x1400210ca  jz      loc_1400214FB
0x1400210d0  test    [rcx+1Ch], r14b
0x1400210d4  jz      loc_1400214FB
0x1400210da  cmp     byte ptr [rcx+19h], 2
0x1400210de  jb      loc_1400214FB
0x1400210e4  mov     rcx, [rcx+10h]
0x1400210e8  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x1400210ef  mov     edx, 1FFh
0x1400210f4  mov     r9d, eax
0x1400210f7  call    WPP_SF_d
0x1400210fc  jmp     loc_1400214FB
0x140021101  lea     rbx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_CsQueue
0x140021108  or      r14, 0FFFFFFFFFFFFFFFFh
0x14002110c  mov     rcx, rbx; lpCriticalSection
0x14002110f  call    cs:__imp_EnterCriticalSection
0x140021115  mov     rsi, cs:?g_QueueListHead@@3U_LIST_ENTRY@@A.Flink; _LIST_ENTRY g_QueueListHead ...
0x14002111c  lea     rax, ?g_QueueListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_QueueListHead
0x140021123  jmp     short loc_14002112E
0x140021125  cmp     [rsi+10h], rbp
0x140021129  jz      short loc_14002117E
0x14002112b  mov     rsi, [rsi]
0x14002112e  cmp     rsi, rax
0x140021131  jnz     short loc_140021125
0x140021133  xor     ebp, ebp
0x140021135  mov     esi, ebp
0x140021137  mov     rcx, rbx; lpCriticalSection
0x14002113a  call    cs:__imp_LeaveCriticalSection
0x140021140  mov     rcx, cs:WPP_GLOBAL_Control
0x140021147  lea     r12, WPP_GLOBAL_Control
0x14002114e  cmp     rcx, r12
0x140021151  jz      short loc_140021174
0x140021153  test    byte ptr [rcx+1Ch], 4
0x140021157  jz      short loc_140021174
0x140021159  cmp     byte ptr [rcx+19h], 2
0x14002115d  jb      short loc_140021174
0x14002115f  mov     rcx, [rcx+10h]
0x140021163  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14002116a  mov     edx, 200h
0x14002116f  call    WPP_SF_
0x140021174  mov     ebx, 1B61h
0x140021179  jmp     loc_140021460
0x14002117e  xor     ebp, ebp
0x140021180  test    rsi, rsi
0x140021183  jz      short loc_140021137
0x140021185  mov     r9, r15; void *
0x140021188  lea     edx, [rbp+1]; int
0x14002118b  mov     r8d, edi; unsigned int
0x14002118e  mov     rcx, rsi; struct _JOB_QUEUE *
0x140021191  call    ?AccessibleJob@@YAHPEAU_JOB_QUEUE@@HKPEAX@Z; AccessibleJob(_JOB_QUEUE *,int,ulong,void *)
0x140021196  test    eax, eax
0x140021198  jnz     short loc_1400211ED
0x14002119a  mov     rcx, rbx; lpCriticalSection
0x14002119d  call    cs:__imp_LeaveCriticalSection
0x1400211a3  mov     ebx, 1B61h
0x1400211a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400211af  lea     r12, WPP_GLOBAL_Control
0x1400211b6  cmp     rcx, r12
0x1400211b9  jz      loc_140021460
0x1400211bf  test    byte ptr [rcx+1Ch], 4
0x1400211c3  jz      loc_140021460
0x1400211c9  cmp     byte ptr [rcx+19h], 2
0x1400211cd  jb      loc_140021460
0x1400211d3  mov     rcx, [rcx+10h]
0x1400211d7  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x1400211de  mov     edx, 201h
0x1400211e3  call    WPP_SF_
0x1400211e8  jmp     loc_140021460
0x1400211ed  mov     rcx, rsi; struct _JOB_QUEUE *
0x1400211f0  call    CreatePreviewFile
0x1400211f5  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400211fc  mov     ebx, eax
0x1400211fe  test    eax, eax
0x140021200  jz      short loc_140021250
0x140021202  call    cs:__imp_LeaveCriticalSection
0x140021208  mov     rcx, cs:WPP_GLOBAL_Control
0x14002120f  lea     r12, WPP_GLOBAL_Control
0x140021216  cmp     rcx, r12
0x140021219  jz      loc_140021460
0x14002121f  test    byte ptr [rcx+1Ch], 4
0x140021223  jz      loc_140021460
0x140021229  cmp     byte ptr [rcx+19h], 2
0x14002122d  jb      loc_140021460
0x140021233  mov     rcx, [rcx+10h]
0x140021237  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14002123e  mov     edx, 202h
0x140021243  mov     r9d, ebx
0x140021246  call    WPP_SF_d
0x14002124b  jmp     loc_140021460
0x140021250  call    cs:__imp_LeaveCriticalSection
0x140021256  mov     rcx, [rsi+258h]
0x14002125d  lea     r8, [rsp+2B8h+FileName]
0x140021262  mov     eax, 7FFFFFFEh
0x140021267  mov     [rsp+2B8h+var_278], 1
0x14002126f  mov     edx, 104h
0x140021274  test    rax, rax
0x140021277  jz      short loc_140021298
0x140021279  movzx   r9d, word ptr [rcx]
0x14002127d  test    r9w, r9w
0x140021281  jz      short loc_140021298
0x140021283  mov     [r8], r9w
0x140021287  add     rcx, 2
0x14002128b  add     r8, 2
0x14002128f  dec     rax
0x140021292  sub     rdx, 1
0x140021296  jnz     short loc_140021274
0x140021298  mov     rax, rdx
0x14002129b  lea     rcx, [r8-2]
0x14002129f  neg     rax
0x1400212a2  sbb     edi, edi
0x1400212a4  not     edi
0x1400212a6  and     edi, 8007007Ah
0x1400212ac  test    rdx, rdx
0x1400212af  cmovnz  rcx, r8
0x1400212b3  mov     [rcx], bp
0x1400212b6  jnz     loc_140021373
0x1400212bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400212c3  lea     r12, WPP_GLOBAL_Control
0x1400212ca  cmp     rcx, r12
0x1400212cd  jz      short loc_1400212F3
0x1400212cf  test    byte ptr [rcx+1Ch], 4
0x1400212d3  jz      short loc_1400212F3
0x1400212d5  cmp     byte ptr [rcx+19h], 2
0x1400212d9  jb      short loc_1400212F3
0x1400212db  mov     rcx, [rcx+10h]
0x1400212df  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x1400212e6  mov     edx, 203h
0x1400212eb  mov     r9d, edi
0x1400212ee  call    WPP_SF_d
0x1400212f3  mov     eax, edi
0x1400212f5  movzx   ebx, di
0x1400212f8  and     eax, 1FFF0000h
0x1400212fd  cmp     eax, 70000h
0x140021302  cmovnz  ebx, edi
0x140021305  jmp     loc_140021460
0x14002130a  lea     rax, [rsp+2B8h+FileName]
0x14002130f  mov     r9d, 1
0x140021315  mov     r8d, edi
0x140021318  mov     qword ptr [rsp+2B8h+var_298], rax
0x14002131d  mov     rdx, rbp
0x140021320  mov     ecx, ebx
0x140021322  call    FindArchivedMessageAfterAccessCheck
0x140021327  xor     ebp, ebp
0x140021329  mov     ebx, eax
0x14002132b  test    eax, eax
0x14002132d  jz      short loc_140021370
0x14002132f  mov     rcx, cs:WPP_GLOBAL_Control
0x140021336  cmp     rcx, r15
0x140021339  jz      loc_1400214EC
0x14002133f  test    [rcx+1Ch], r14b
0x140021343  jz      loc_1400214EC
0x140021349  cmp     byte ptr [rcx+19h], 2
0x14002134d  jb      loc_1400214EC
0x140021353  mov     rcx, [rcx+10h]
0x140021357  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14002135e  mov     edx, 204h
0x140021363  mov     r9d, eax
0x140021366  call    WPP_SF_d
0x14002136b  jmp     loc_1400214EC
0x140021370  mov     r15, rbp
0x140021373  mov     [rsp+2B8h+var_290], 80h; int
0x14002137b  lea     rcx, [rsp+2B8h+FileName]; lpFileName
0x140021380  mov     edx, 80000000h; dwDesiredAccess
0x140021385  mov     [rsp+2B8h+var_298], 3; DWORD
0x14002138d  mov     r8d, 1; dwShareMode
0x140021393  call    InternalSafeCreateFile
0x140021398  mov     r14, rax
0x14002139b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002139f  jnz     short loc_1400213F4
0x1400213a1  call    cs:__imp_GetLastError
0x1400213a7  mov     ebx, eax
0x1400213a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400213b0  lea     r12, WPP_GLOBAL_Control
0x1400213b7  cmp     rcx, r12
0x1400213ba  jz      loc_14002145B
0x1400213c0  test    byte ptr [rcx+1Ch], 4
0x1400213c4  jz      loc_14002145B
0x1400213ca  cmp     byte ptr [rcx+19h], 2
0x1400213ce  jb      loc_14002145B
0x1400213d4  mov     rcx, [rcx+10h]
0x1400213d8  lea     r9, [rsp+2B8h+FileName]
0x1400213dd  mov     edx, 205h
0x1400213e2  mov     [rsp+2B8h+var_298], eax
0x1400213e6  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x1400213ed  call    WPP_SF_Sd
0x1400213f2  jmp     short loc_14002145B
0x1400213f4  xor     r9d, r9d; unsigned __int16 *
0x1400213f7  mov     qword ptr [rsp+2B8h+var_298], rsi; struct _JOB_QUEUE *
0x1400213fc  xor     r8d, r8d; int
0x1400213ff  mov     rdx, rax; void *
0x140021402  mov     rcx, r13; void *
0x140021405  call    ?CreateNewCopyHandle@@YAPEAU_HANDLE_ENTRY@@PEAX0HPEBGPEAU_JOB_QUEUE@@@Z; CreateNewCopyHandle(void *,void *,int,ushort const *,_JOB_QUEUE *)
0x14002140a  test    rax, rax
0x14002140d  jnz     short loc_140021450
0x14002140f  call    cs:__imp_GetLastError
0x140021415  mov     ebx, eax
0x140021417  mov     rcx, cs:WPP_GLOBAL_Control
0x14002141e  lea     r12, WPP_GLOBAL_Control
0x140021425  cmp     rcx, r12
0x140021428  jz      short loc_14002145B
0x14002142a  test    byte ptr [rcx+1Ch], 4
0x14002142e  jz      short loc_14002145B
0x140021430  cmp     byte ptr [rcx+19h], 2
0x140021434  jb      short loc_14002145B
0x140021436  mov     rcx, [rcx+10h]
0x14002143a  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140021441  mov     edx, 206h
0x140021446  mov     r9d, eax
0x140021449  call    WPP_SF_d
0x14002144e  jmp     short loc_14002145B
0x140021450  mov     [r12], rax
0x140021454  lea     r12, WPP_GLOBAL_Control
0x14002145b  test    r15, r15
0x14002145e  jz      short loc_140021468
0x140021460  mov     rcx, r15; lpMem
0x140021463  call    pMemFree
  ... truncated ...
```
