# CldHsmInitialize

- ea: `0x140087080`
- end: `0x140087386`
- name: `CldHsmInitialize`
- size: `774`
- prototype: `__int64 __fastcall(struct _FLT_FILTER *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x140003c50`
- `0x14000d95c`
- `0x1400131d4`
- `0x140037aa4`
- `0x140040ad0`
- `0x140087080`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x140087306`
- `ntoskrnl!ExUuidCreate` at `0x140087306`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140087167`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140087196`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400871c5`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400871f4`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140087227`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14008725a`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14008728d`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140087167`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140087196`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400871c5`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400871f4`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140087227`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14008725a`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14008728d`

## pseudocode

```c
__int64 __fastcall CldHsmInitialize(struct _FLT_FILTER *a1)
{
  int IsVailSupported; // ebx
  PDEVICE_OBJECT v2; // rcx
  __int64 v3; // rdx
  int v4; // edi
  NTSTATUS v5; // eax
  char v7; // [rsp+50h] [rbp+8h] BYREF

  v7 = 0;
  Globals = a1;
  IsVailSupported = CldStreamInitialize();
  HsmDbgBreakOnStatus((unsigned int)IsVailSupported);
  if ( IsVailSupported >= 0 )
  {
    IsVailSupported = CldPortInitialize();
    HsmDbgBreakOnStatus((unsigned int)IsVailSupported);
    if ( IsVailSupported >= 0 )
    {
      ExInitializePagedLookasideList(&stru_140028880, 0, 0, 0x200u, 0x30u, 0x72726C43u, 0);
      ExInitializePagedLookasideList(&Lookaside, 0, 0, 0x200u, 0x178u, 0x72726C43u, 0);
      ExInitializePagedLookasideList(&stru_140028980, 0, 0, 0x200u, 0x130u, 0x72726C43u, 0);
      ExInitializePagedLookasideList(&stru_140028A00, 0, 0, 0x200u, 0x138u, 0x72726C43u, 0);
      ExInitializePagedLookasideList(&stru_140028A80, 0, 0, 0x200u, 0x48u, 0x63666C43u, 0);
      ExInitializePagedLookasideList(&stru_140028B00, 0, 0, 0x200u, 0x28u, 0x63536C43u, 0);
      ExInitializePagedLookasideList(&stru_140028B80, 0, 0, 0x200u, 0x10u, 0x63486C43u, 0);
      byte_140028879 = 1;
      byte_140028878 = 1;
      byte_140028768 = 0;
      IsVailSupported = HsmOsIsVailSupported(&v7);
      if ( IsVailSupported >= 0 )
      {
        if ( v7 )
        {
          v4 = 0;
          while ( 1 )
          {
            v5 = ExUuidCreate(&Uuid);
            IsVailSupported = v5;
            if ( !v5 || v5 == 1073872982 )
            {
              byte_140028768 = 1;
              return 0;
            }
            if ( v5 != -1073741267 )
              break;
            if ( (unsigned int)++v4 >= 0x64 )
              goto LABEL_25;
          }
          if ( v5 >= 0 )
            return (unsigned int)IsVailSupported;
LABEL_25:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              13,
              WPP_6a3f9e12555c34a12273f84e1e075d2c_Traceguids,
              (unsigned int)v5);
          }
          return 0;
        }
      }
      else
      {
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v3 = 12;
          goto LABEL_6;
        }
      }
    }
    else
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v3 = 11;
        goto LABEL_6;
      }
    }
  }
  else
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v3 = 10;
LABEL_6:
      WPP_SF_d(v2->AttachedDevice, v3, WPP_6a3f9e12555c34a12273f84e1e075d2c_Traceguids, (unsigned int)IsVailSupported);
    }
  }
  return (unsigned int)IsVailSupported;
}

```

## disassembly

```asm
0x140087080  mov     [rsp+arg_8], rbx
0x140087085  push    rdi
0x140087086  sub     rsp, 40h
0x14008708a  mov     [rsp+48h+arg_0], 0
0x14008708f  mov     cs:Globals, rcx
0x140087096  call    CldStreamInitialize
0x14008709b  mov     ecx, eax
0x14008709d  mov     ebx, eax
0x14008709f  call    HsmDbgBreakOnStatus
0x1400870a4  test    ebx, ebx
0x1400870a6  jns     short loc_1400870F3
0x1400870a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400870af  lea     rax, WPP_GLOBAL_Control
0x1400870b6  cmp     rcx, rax
0x1400870b9  jz      loc_140087378
0x1400870bf  test    dword ptr [rcx+2Ch], 100h
0x1400870c6  jz      loc_140087378
0x1400870cc  cmp     byte ptr [rcx+29h], 2
0x1400870d0  jb      loc_140087378
0x1400870d6  mov     edx, 0Ah
0x1400870db  mov     rcx, [rcx+18h]
0x1400870df  lea     r8, WPP_6a3f9e12555c34a12273f84e1e075d2c_Traceguids
0x1400870e6  mov     r9d, ebx
0x1400870e9  call    WPP_SF_d
0x1400870ee  jmp     loc_140087378
0x1400870f3  call    CldPortInitialize
0x1400870f8  mov     ecx, eax
0x1400870fa  mov     ebx, eax
0x1400870fc  call    HsmDbgBreakOnStatus
0x140087101  test    ebx, ebx
0x140087103  jns     short loc_14008713A
0x140087105  mov     rcx, cs:WPP_GLOBAL_Control
0x14008710c  lea     rax, WPP_GLOBAL_Control
0x140087113  cmp     rcx, rax
0x140087116  jz      loc_140087378
0x14008711c  test    dword ptr [rcx+2Ch], 100h
0x140087123  jz      loc_140087378
0x140087129  cmp     byte ptr [rcx+29h], 2
0x14008712d  jb      loc_140087378
0x140087133  mov     edx, 0Bh
0x140087138  jmp     short loc_1400870DB
0x14008713a  xor     eax, eax
0x14008713c  lea     rcx, stru_140028880; Lookaside
0x140087143  mov     [rsp+48h+Depth], ax; Depth
0x140087148  mov     ebx, 72726C43h
0x14008714d  mov     edi, 200h
0x140087152  mov     [rsp+48h+Tag], ebx; Tag
0x140087156  mov     r9d, edi; Flags
0x140087159  mov     [rsp+48h+Size], 30h ; '0'; Size
0x140087162  xor     r8d, r8d; Free
0x140087165  xor     edx, edx; Allocate
0x140087167  call    cs:__imp_ExInitializePagedLookasideList
0x14008716e  nop     dword ptr [rax+rax+00h]
0x140087173  xor     eax, eax
0x140087175  lea     rcx, Lookaside; Lookaside
0x14008717c  mov     [rsp+48h+Depth], ax; Depth
0x140087181  mov     r9d, edi; Flags
0x140087184  mov     [rsp+48h+Tag], ebx; Tag
0x140087188  xor     r8d, r8d; Free
0x14008718b  xor     edx, edx; Allocate
0x14008718d  mov     [rsp+48h+Size], 178h; Size
0x140087196  call    cs:__imp_ExInitializePagedLookasideList
0x14008719d  nop     dword ptr [rax+rax+00h]
0x1400871a2  xor     eax, eax
0x1400871a4  lea     rcx, stru_140028980; Lookaside
0x1400871ab  mov     [rsp+48h+Depth], ax; Depth
0x1400871b0  mov     r9d, edi; Flags
0x1400871b3  mov     [rsp+48h+Tag], ebx; Tag
0x1400871b7  xor     r8d, r8d; Free
0x1400871ba  xor     edx, edx; Allocate
0x1400871bc  mov     [rsp+48h+Size], 130h; Size
0x1400871c5  call    cs:__imp_ExInitializePagedLookasideList
0x1400871cc  nop     dword ptr [rax+rax+00h]
0x1400871d1  xor     eax, eax
0x1400871d3  lea     rcx, stru_140028A00; Lookaside
0x1400871da  mov     [rsp+48h+Depth], ax; Depth
0x1400871df  mov     r9d, edi; Flags
0x1400871e2  mov     [rsp+48h+Tag], ebx; Tag
0x1400871e6  xor     r8d, r8d; Free
0x1400871e9  xor     edx, edx; Allocate
0x1400871eb  mov     [rsp+48h+Size], 138h; Size
0x1400871f4  call    cs:__imp_ExInitializePagedLookasideList
0x1400871fb  nop     dword ptr [rax+rax+00h]
0x140087200  xor     eax, eax
0x140087202  lea     rcx, stru_140028A80; Lookaside
0x140087209  mov     [rsp+48h+Depth], ax; Depth
0x14008720e  mov     r9d, edi; Flags
0x140087211  mov     [rsp+48h+Tag], 63666C43h; Tag
0x140087219  xor     r8d, r8d; Free
0x14008721c  xor     edx, edx; Allocate
0x14008721e  mov     [rsp+48h+Size], 48h ; 'H'; Size
0x140087227  call    cs:__imp_ExInitializePagedLookasideList
0x14008722e  nop     dword ptr [rax+rax+00h]
0x140087233  xor     eax, eax
0x140087235  lea     rcx, stru_140028B00; Lookaside
0x14008723c  mov     [rsp+48h+Depth], ax; Depth
0x140087241  mov     r9d, edi; Flags
0x140087244  mov     [rsp+48h+Tag], 63536C43h; Tag
0x14008724c  xor     r8d, r8d; Free
0x14008724f  xor     edx, edx; Allocate
0x140087251  mov     [rsp+48h+Size], 28h ; '('; Size
0x14008725a  call    cs:__imp_ExInitializePagedLookasideList
0x140087261  nop     dword ptr [rax+rax+00h]
0x140087266  xor     eax, eax
0x140087268  lea     rcx, stru_140028B80; Lookaside
0x14008726f  mov     [rsp+48h+Depth], ax; Depth
0x140087274  mov     r9d, edi; Flags
0x140087277  mov     [rsp+48h+Tag], 63486C43h; Tag
0x14008727f  xor     r8d, r8d; Free
0x140087282  xor     edx, edx; Allocate
0x140087284  mov     [rsp+48h+Size], 10h; Size
0x14008728d  call    cs:__imp_ExInitializePagedLookasideList
0x140087294  nop     dword ptr [rax+rax+00h]
0x140087299  mov     cs:byte_140028879, 1
0x1400872a0  lea     rcx, [rsp+48h+arg_0]
0x1400872a5  mov     cs:byte_140028878, 1
0x1400872ac  mov     cs:byte_140028768, 0
0x1400872b3  call    HsmOsIsVailSupported
0x1400872b8  mov     ebx, eax
0x1400872ba  test    eax, eax
0x1400872bc  jns     short loc_1400872F6
0x1400872be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400872c5  lea     rax, WPP_GLOBAL_Control
0x1400872cc  cmp     rcx, rax
0x1400872cf  jz      loc_140087378
0x1400872d5  test    dword ptr [rcx+2Ch], 100h
0x1400872dc  jz      loc_140087378
0x1400872e2  cmp     byte ptr [rcx+29h], 2
0x1400872e6  jb      loc_140087378
0x1400872ec  mov     edx, 0Ch
0x1400872f1  jmp     loc_1400870DB
0x1400872f6  cmp     [rsp+48h+arg_0], 0
0x1400872fb  jz      short loc_140087378
0x1400872fd  xor     edi, edi
0x1400872ff  lea     rcx, Uuid; Uuid
0x140087306  call    cs:__imp_ExUuidCreate
0x14008730d  nop     dword ptr [rax+rax+00h]
0x140087312  mov     ebx, eax
0x140087314  test    eax, eax
0x140087316  jz      short loc_14008736F
0x140087318  cmp     eax, 40020056h
0x14008731d  jz      short loc_14008736F
0x14008731f  cmp     eax, 0C000022Dh
0x140087324  jnz     short loc_14008732F
0x140087326  inc     edi
0x140087328  cmp     edi, 64h ; 'd'
0x14008732b  jb      short loc_1400872FF
0x14008732d  jmp     short loc_140087333
0x14008732f  test    eax, eax
0x140087331  jns     short loc_140087378
0x140087333  mov     rcx, cs:WPP_GLOBAL_Control
0x14008733a  lea     rax, WPP_GLOBAL_Control
0x140087341  cmp     rcx, rax
0x140087344  jz      short loc_140087376
0x140087346  test    dword ptr [rcx+2Ch], 100h
0x14008734d  jz      short loc_140087376
0x14008734f  cmp     byte ptr [rcx+29h], 2
0x140087353  jb      short loc_140087376
0x140087355  mov     rcx, [rcx+18h]
0x140087359  lea     r8, WPP_6a3f9e12555c34a12273f84e1e075d2c_Traceguids
0x140087360  mov     edx, 0Dh
0x140087365  mov     r9d, ebx
0x140087368  call    WPP_SF_d
0x14008736d  jmp     short loc_140087376
0x14008736f  mov     cs:byte_140028768, 1
0x140087376  xor     ebx, ebx
0x140087378  mov     eax, ebx
0x14008737a  mov     rbx, [rsp+48h+arg_8]
0x14008737f  add     rsp, 40h
0x140087383  pop     rdi
0x140087384  retn
```
