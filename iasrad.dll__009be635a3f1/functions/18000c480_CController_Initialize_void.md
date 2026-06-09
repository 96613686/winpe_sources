# CController::Initialize(void)

- ea: `0x18000c480`
- end: `0x18000c60e`
- name: `?Initialize@CController@@UEAAJXZ`
- size: `398`
- prototype: `__int64 __fastcall(CController *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800094e4`
- `0x18000c480`
- `0x18000c838`
- `0x18001d31c`
- `0x180030010`

## string_xrefs

- `0x18000c4b0`: `Initializing Radius component....`
- `0x18000c50a`: `Unable to initialize Radius Component in this state`
- `0x18000c5d3`: `Radius component initialized.`

## pseudocode

```c
__int64 __fastcall CController::Initialize(CController *this)
{
  PVOID *v2; // rax
  int v3; // ecx
  __int64 result; // rax
  int v5; // edi

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Initializing Radius component....");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = *((_DWORD *)this + 322);
  if ( v3 == 2 )
    return 0;
  if ( v3 != 1 )
  {
    if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 2u && (*((_DWORD *)v2 + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Unable to initialize Radius Component in this state");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
    }
    return 2147549183LL;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 23) + 56LL))(*((_QWORD *)this + 23));
  if ( v5 >= 0 )
  {
    result = CController::InternalInit(this);
    if ( (int)result < 0 )
      return result;
    *((_DWORD *)this + 322) = 2;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Radius component initialized.");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("InfoBase initialization failed");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000c480  push    rbx
0x18000c482  push    rsi
0x18000c483  push    rdi
0x18000c484  push    r14
0x18000c486  sub     rsp, 28h
0x18000c48a  mov     rbx, rcx
0x18000c48d  mov     rax, cs:WPP_GLOBAL_Control
0x18000c494  lea     r14, WPP_GLOBAL_Control
0x18000c49b  mov     esi, 100h
0x18000c4a0  cmp     rax, r14
0x18000c4a3  jz      short loc_18000C4E6
0x18000c4a5  cmp     byte ptr [rax+19h], 4
0x18000c4a9  jb      short loc_18000C4E6
0x18000c4ab  test    [rax+1Ch], esi
0x18000c4ae  jz      short loc_18000C4E6
0x18000c4b0  lea     rcx, aInitializingRa; "Initializing Radius component...."
0x18000c4b7  call    WppDbgPrint
0x18000c4bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4c3  lea     r9, aNpsrad; "NPSRAD"
0x18000c4ca  mov     edx, 31h ; '1'
0x18000c4cf  lea     r8, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000c4d6  mov     rcx, [rcx+10h]
0x18000c4da  call    WPP_SF_s
0x18000c4df  mov     rax, cs:WPP_GLOBAL_Control
0x18000c4e6  mov     ecx, [rbx+508h]
0x18000c4ec  cmp     ecx, 2
0x18000c4ef  jz      loc_18000C602
0x18000c4f5  cmp     ecx, 1
0x18000c4f8  jz      short loc_18000C543
0x18000c4fa  cmp     rax, r14
0x18000c4fd  jz      short loc_18000C539
0x18000c4ff  cmp     byte ptr [rax+19h], 2
0x18000c503  jb      short loc_18000C539
0x18000c505  test    [rax+1Ch], esi
0x18000c508  jz      short loc_18000C539
0x18000c50a  lea     rcx, aUnableToInitia_0; "Unable to initialize Radius Component i"...
0x18000c511  call    WppDbgPrint
0x18000c516  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c51d  lea     r9, aNpsrad; "NPSRAD"
0x18000c524  mov     edx, 32h ; '2'
0x18000c529  lea     r8, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000c530  mov     rcx, [rcx+10h]
0x18000c534  call    WPP_SF_s
0x18000c539  mov     eax, 8000FFFFh
0x18000c53e  jmp     loc_18000C604
0x18000c543  mov     rcx, [rbx+0B8h]
0x18000c54a  mov     rax, [rcx]
0x18000c54d  mov     rax, [rax+38h]
0x18000c551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c556  mov     edi, eax
0x18000c558  test    eax, eax
0x18000c55a  jns     short loc_18000C5A6
0x18000c55c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c563  cmp     rcx, r14
0x18000c566  jz      short loc_18000C5A2
0x18000c568  cmp     byte ptr [rcx+19h], 2
0x18000c56c  jb      short loc_18000C5A2
0x18000c56e  test    [rcx+1Ch], esi
0x18000c571  jz      short loc_18000C5A2
0x18000c573  lea     rcx, aInfobaseInitia; "InfoBase initialization failed"
0x18000c57a  call    WppDbgPrint
0x18000c57f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c586  lea     r9, aNpsrad; "NPSRAD"
0x18000c58d  mov     edx, 33h ; '3'
0x18000c592  lea     r8, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000c599  mov     rcx, [rcx+10h]
0x18000c59d  call    WPP_SF_s
0x18000c5a2  mov     eax, edi
0x18000c5a4  jmp     short loc_18000C604
0x18000c5a6  mov     rcx, rbx; this
0x18000c5a9  call    ?InternalInit@CController@@AEAAJXZ; CController::InternalInit(void)
0x18000c5ae  test    eax, eax
0x18000c5b0  js      short loc_18000C604
0x18000c5b2  mov     dword ptr [rbx+508h], 2
0x18000c5bc  mov     rax, cs:WPP_GLOBAL_Control
0x18000c5c3  cmp     rax, r14
0x18000c5c6  jz      short loc_18000C602
0x18000c5c8  cmp     byte ptr [rax+19h], 4
0x18000c5cc  jb      short loc_18000C602
0x18000c5ce  test    [rax+1Ch], esi
0x18000c5d1  jz      short loc_18000C602
0x18000c5d3  lea     rcx, aRadiusComponen_2; "Radius component initialized."
0x18000c5da  call    WppDbgPrint
0x18000c5df  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5e6  lea     r9, aNpsrad; "NPSRAD"
0x18000c5ed  mov     edx, 34h ; '4'
0x18000c5f2  lea     r8, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000c5f9  mov     rcx, [rcx+10h]
0x18000c5fd  call    WPP_SF_s
0x18000c602  xor     eax, eax
0x18000c604  add     rsp, 28h
0x18000c608  pop     r14
0x18000c60a  pop     rdi
0x18000c60b  pop     rsi
0x18000c60c  pop     rbx
0x18000c60d  retn
```
