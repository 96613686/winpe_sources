# CClfsManagedLog::AddContainersForGrowth(CClfsManagedLogClient *,unsigned __int64 const &,unsigned __int64 &)

- ea: `0x140032294`
- end: `0x140032527`
- name: `?AddContainersForGrowth@CClfsManagedLog@@AEAAJPEAVCClfsManagedLogClient@@AEB_KAEA_K@Z`
- size: `659`
- prototype: `__int64 __fastcall(CClfsManagedLog *__hidden this, struct CClfsManagedLogClient *, const unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140074644`

## callees

- `0x14000ed64`
- `0x14001058c`
- `0x140011d90`
- `0x140032294`
- `0x14005e910`
- `0x14006ea3c`
- `0x1400757c0`
- `0x140078c40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400324ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400324ee`
- `ntoskrnl!PsRevertToSelf` at `0x14003246c`
- `ntoskrnl!PsRevertToSelf` at `0x14003246c`
- `ntoskrnl!SeImpersonateClientEx` at `0x14003232c`
- `ntoskrnl!SeImpersonateClientEx` at `0x14003232c`

## pseudocode

```c
int __fastcall CClfsManagedLog::AddContainersForGrowth(
        FILE_OBJECT **this,
        struct CClfsManagedLogClient *a2,
        const unsigned __int64 *a3,
        unsigned __int64 *a4)
{
  unsigned __int64 ContainerSizeInBytes; // rax
  __int64 *v8; // r8
  __int64 v9; // r15
  _QWORD *v10; // r9
  int result; // eax
  int v12; // ebx
  int v13; // r14d
  FILE_OBJECT *v14; // rbx
  NTSTATUS v15; // eax
  unsigned __int64 *v16; // rdi
  int LogContainerSize; // eax
  __int64 v18; // [rsp+28h] [rbp-20h]
  UNICODE_STRING rguszContainerPath; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int64 pcbContainer; // [rsp+A0h] [rbp+58h] BYREF

  ContainerSizeInBytes = CClfsManagedLog::GetContainerSizeInBytes((CClfsManagedLog *)this);
  v9 = *v8;
  pcbContainer = ContainerSizeInBytes;
  *(_QWORD *)&rguszContainerPath.Length = 0;
  rguszContainerPath.Buffer = 0;
  *v10 = 0;
  result = CClfsManagedLog::AllocateAndBuildContainerNameTemplate((CClfsManagedLog *)this, &rguszContainerPath);
  v12 = result;
  if ( result >= 0 )
  {
    if ( v9 )
    {
      while ( 2 )
      {
        v13 = 3;
        while ( v13 )
        {
          v12 = CClfsManagedLog::FixupContainerName((CClfsManagedLog *)this, &rguszContainerPath);
          if ( v12 < 0 )
            goto LABEL_36;
          if ( a2 )
            SeImpersonateClientEx((PSECURITY_CLIENT_CONTEXT)((char *)a2 + 128), 0);
          v14 = this[42];
          if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
          {
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              66,
              (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
              (unsigned int)"ClfsAddLogContainer",
              136);
          }
          if ( v14 )
          {
            v15 = ClfsAddLogContainerSet(v14, 1u, &pcbContainer, &rguszContainerPath);
            v12 = v15;
            if ( v15 >= 0 )
            {
              if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
              {
                WPP_SF_sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 3),
                  69,
                  (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
                  (unsigned int)"ClfsAddLogContainer",
                  165);
              }
            }
            else if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
                   && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
            {
              LODWORD(v18) = v15;
              WPP_SF_slD(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                68,
                (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
                (unsigned int)"ClfsAddLogContainer",
                161,
                v18);
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
            {
              LODWORD(v18) = -1073741811;
              WPP_SF_slD(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                67,
                (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
                (unsigned int)"ClfsAddLogContainer",
                148,
                v18);
            }
            v12 = -1073741811;
          }
          if ( a2 )
            PsRevertToSelf();
          if ( v12 >= 0 )
            goto LABEL_33;
          --v13;
          if ( v12 == -1073741811 )
          {
            v16 = (unsigned __int64 *)(this + 69);
            LogContainerSize = CClfsManagedLog::QueryLogContainerSize(
                                 (CClfsManagedLog *)this,
                                 (unsigned __int64 *)this + 69);
            if ( LogContainerSize < 0 )
            {
              v12 = LogContainerSize;
              goto LABEL_36;
            }
            if ( pcbContainer >= *v16 )
            {
              if ( !*v16 )
                *v16 = pcbContainer;
            }
            else
            {
              pcbContainer = *v16;
              v13 = 3;
            }
          }
        }
        if ( v12 < 0 )
          break;
LABEL_33:
        ++*a4;
        if ( --v9 )
          continue;
        break;
      }
    }
LABEL_36:
    if ( rguszContainerPath.Buffer )
      ExFreePoolWithTag(rguszContainerPath.Buffer, 0);
    if ( v12 >= 0 && !this[69] )
      CClfsManagedLog::QueryLogContainerSize((CClfsManagedLog *)this, (unsigned __int64 *)this + 69);
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x140032294  push    rbp
0x140032296  push    rbx
0x140032297  push    rsi
0x140032298  push    rdi
0x140032299  push    r12
0x14003229b  push    r13
0x14003229d  push    r14
0x14003229f  push    r15
0x1400322a1  mov     rbp, rsp
0x1400322a4  sub     rsp, 48h
0x1400322a8  mov     r12, r9
0x1400322ab  mov     r13, rdx
0x1400322ae  mov     rsi, rcx
0x1400322b1  call    ?GetContainerSizeInBytes@CClfsManagedLog@@AEAA_KXZ; CClfsManagedLog::GetContainerSizeInBytes(void)
0x1400322b6  mov     r15, [r8]
0x1400322b9  lea     rdx, [rbp+rguszContainerPath]; struct _UNICODE_STRING *
0x1400322bd  mov     [rbp+pcbContainer], rax
0x1400322c1  mov     rcx, rsi; this
0x1400322c4  xor     eax, eax
0x1400322c6  mov     qword ptr [rbp+rguszContainerPath.Length], rax
0x1400322ca  mov     [rbp+rguszContainerPath.Buffer], rax
0x1400322ce  mov     [r9], rax
0x1400322d1  call    ?AllocateAndBuildContainerNameTemplate@CClfsManagedLog@@AEAAJPEAU_UNICODE_STRING@@@Z; CClfsManagedLog::AllocateAndBuildContainerNameTemplate(_UNICODE_STRING *)
0x1400322d6  mov     ebx, eax
0x1400322d8  test    eax, eax
0x1400322da  js      loc_140032515
0x1400322e0  test    r15, r15
0x1400322e3  jz      loc_1400324E3
0x1400322e9  lea     rdi, WPP_GLOBAL_Control
0x1400322f0  mov     r14d, 3
0x1400322f6  jmp     short loc_1400322FF
0x1400322f8  lea     rdi, WPP_GLOBAL_Control
0x1400322ff  test    r14d, r14d
0x140032302  jz      loc_1400324CD
0x140032308  lea     rdx, [rbp+rguszContainerPath]; struct _UNICODE_STRING *
0x14003230c  mov     rcx, rsi; this
0x14003230f  call    ?FixupContainerName@CClfsManagedLog@@AEAAJPEAU_UNICODE_STRING@@@Z; CClfsManagedLog::FixupContainerName(_UNICODE_STRING *)
0x140032314  mov     ebx, eax
0x140032316  test    eax, eax
0x140032318  js      loc_1400324E3
0x14003231e  test    r13, r13
0x140032321  jz      short loc_140032338
0x140032323  lea     rcx, [r13+80h]; ClientContext
0x14003232a  xor     edx, edx; ServerThread
0x14003232c  call    cs:__imp_SeImpersonateClientEx
0x140032333  nop     dword ptr [rax+rax+00h]
0x140032338  mov     rbx, [rsi+150h]
0x14003233f  mov     rcx, cs:WPP_GLOBAL_Control
0x140032346  cmp     rcx, rdi
0x140032349  jz      short loc_140032378
0x14003234b  test    dword ptr [rcx+2Ch], 4000000h
0x140032352  jz      short loc_140032378
0x140032354  mov     rcx, [rcx+18h]
0x140032358  lea     r9, aClfsaddlogcont_0; "ClfsAddLogContainer"
0x14003235f  mov     edx, 42h ; 'B'
0x140032364  mov     [rsp+48h+var_28], 888h
0x14003236c  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140032373  call    WPP_SF_sd
0x140032378  test    rbx, rbx
0x14003237b  jz      loc_140032421
0x140032381  mov     edx, 1; cContainers
0x140032386  lea     r9, [rbp+rguszContainerPath]; rguszContainerPath
0x14003238a  lea     r8, [rbp+pcbContainer]; pcbContainer
0x14003238e  mov     rcx, rbx; plfoLog
0x140032391  call    ClfsAddLogContainerSet
0x140032396  mov     ebx, eax
0x140032398  test    eax, eax
0x14003239a  jns     short loc_1400323E6
0x14003239c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400323a3  cmp     rcx, rdi
0x1400323a6  jz      loc_140032467
0x1400323ac  test    dword ptr [rcx+2Ch], 4000000h
0x1400323b3  jz      loc_140032467
0x1400323b9  mov     rcx, [rcx+18h]
0x1400323bd  lea     r9, aClfsaddlogcont_0; "ClfsAddLogContainer"
0x1400323c4  mov     dword ptr [rsp+48h+var_20], eax
0x1400323c8  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x1400323cf  mov     edx, 44h ; 'D'
0x1400323d4  mov     [rsp+48h+var_28], 8A1h
0x1400323dc  call    WPP_SF_slD
0x1400323e1  jmp     loc_140032467
0x1400323e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400323ed  cmp     rcx, rdi
0x1400323f0  jz      short loc_140032467
0x1400323f2  test    dword ptr [rcx+2Ch], 4000000h
0x1400323f9  jz      short loc_140032467
0x1400323fb  mov     rcx, [rcx+18h]
0x1400323ff  lea     r9, aClfsaddlogcont_0; "ClfsAddLogContainer"
0x140032406  mov     edx, 45h ; 'E'
0x14003240b  mov     [rsp+48h+var_28], 8A5h
0x140032413  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14003241a  call    WPP_SF_sd
0x14003241f  jmp     short loc_140032467
0x140032421  mov     rcx, cs:WPP_GLOBAL_Control
0x140032428  cmp     rcx, rdi
0x14003242b  jz      short loc_140032462
0x14003242d  test    dword ptr [rcx+2Ch], 4000000h
0x140032434  jz      short loc_140032462
0x140032436  mov     rcx, [rcx+18h]
0x14003243a  lea     r9, aClfsaddlogcont_0; "ClfsAddLogContainer"
0x140032441  mov     edx, 43h ; 'C'
0x140032446  mov     dword ptr [rsp+48h+var_20], 0C000000Dh
0x14003244e  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140032455  mov     [rsp+48h+var_28], 894h
0x14003245d  call    WPP_SF_slD
0x140032462  mov     ebx, 0C000000Dh
0x140032467  test    r13, r13
0x14003246a  jz      short loc_140032478
0x14003246c  call    cs:__imp_PsRevertToSelf
0x140032473  nop     dword ptr [rax+rax+00h]
0x140032478  test    ebx, ebx
0x14003247a  jns     short loc_1400324D1
0x14003247c  dec     r14d
0x14003247f  cmp     ebx, 0C000000Dh
0x140032485  jnz     loc_1400322FF
0x14003248b  lea     rdi, [rsi+228h]
0x140032492  mov     rcx, rsi; this
0x140032495  mov     rdx, rdi; unsigned __int64 *
0x140032498  call    ?QueryLogContainerSize@CClfsManagedLog@@AEAAJAEA_K@Z; CClfsManagedLog::QueryLogContainerSize(unsigned __int64 &)
0x14003249d  test    eax, eax
0x14003249f  js      short loc_1400324E1
0x1400324a1  mov     rax, [rdi]
0x1400324a4  mov     rcx, [rbp+pcbContainer]
0x1400324a8  cmp     rcx, rax
0x1400324ab  jnb     short loc_1400324BC
0x1400324ad  mov     [rbp+pcbContainer], rax
0x1400324b1  mov     r14d, 3
0x1400324b7  jmp     loc_1400322F8
0x1400324bc  test    rax, rax
0x1400324bf  jnz     loc_1400322F8
0x1400324c5  mov     [rdi], rcx
0x1400324c8  jmp     loc_1400322F8
0x1400324cd  test    ebx, ebx
0x1400324cf  js      short loc_1400324E3
0x1400324d1  inc     qword ptr [r12]
0x1400324d5  sub     r15, 1
0x1400324d9  jnz     loc_1400322F0
0x1400324df  jmp     short loc_1400324E3
0x1400324e1  mov     ebx, eax
0x1400324e3  mov     rcx, [rbp+rguszContainerPath.Buffer]; P
0x1400324e7  test    rcx, rcx
0x1400324ea  jz      short loc_1400324FA
0x1400324ec  xor     edx, edx; Tag
0x1400324ee  call    cs:__imp_ExFreePoolWithTag
0x1400324f5  nop     dword ptr [rax+rax+00h]
0x1400324fa  test    ebx, ebx
0x1400324fc  js      short loc_140032513
0x1400324fe  lea     rdx, [rsi+228h]; unsigned __int64 *
0x140032505  cmp     qword ptr [rdx], 0
0x140032509  jnz     short loc_140032513
0x14003250b  mov     rcx, rsi; this
0x14003250e  call    ?QueryLogContainerSize@CClfsManagedLog@@AEAAJAEA_K@Z; CClfsManagedLog::QueryLogContainerSize(unsigned __int64 &)
0x140032513  mov     eax, ebx
0x140032515  add     rsp, 48h
0x140032519  pop     r15
0x14003251b  pop     r14
0x14003251d  pop     r13
0x14003251f  pop     r12
0x140032521  pop     rdi
0x140032522  pop     rsi
0x140032523  pop     rbx
0x140032524  pop     rbp
0x140032525  retn
```
