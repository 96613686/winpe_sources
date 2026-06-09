# RetrieveCurrentDerivedCredentialWithRetry(int,_LUID *,_GUID *,int,uchar *,ulong,uchar * const,ulong *)

- ea: `0x180012710`
- end: `0x180012832`
- name: `?RetrieveCurrentDerivedCredentialWithRetry@@YAKHPEAU_LUID@@PEAU_GUID@@HPEAEKQEAEPEAK@Z`
- size: `290`
- prototype: `__int64 __fastcall(__int64, struct _LUID *, struct _GUID *, int, unsigned __int8 *, ULONG cbInput, unsigned __int8 *const, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004e60`

## callees

- `0x180007f10`
- `0x180012710`
- `0x180012838`
- `0x18001eb8c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180012765`
- `ntdll!RtlNtStatusToDosError` at `0x180012765`

## string_xrefs

- `0x1800127a1`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x180012818`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`

## pseudocode

```c
__int64 __fastcall RetrieveCurrentDerivedCredentialWithRetry(
        __int64 a1,
        struct _LUID *a2,
        struct _GUID *a3,
        int a4,
        unsigned __int8 *a5,
        ULONG cbInput,
        unsigned __int8 *const a7,
        unsigned int *a8)
{
  DWORD CurrentDerivedCredential; // ebx
  int v11; // edx
  __int64 v13; // rcx
  DWORD v14; // eax
  __int64 v15; // r9
  __int64 v16; // rcx

  CurrentDerivedCredential = RetrieveCurrentDerivedCredential(a1, a2, a3, a4, a5, cbInput, a7, a8);
  if ( CurrentDerivedCredential == RtlNtStatusToDosError(-1073739508) )
  {
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        v11,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwError",
        CurrentDerivedCredential,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp",
        232);
    v14 = RetrieveCurrentDerivedCredential(v13, a2, 0, a4, a5, cbInput, a7, a8);
    CurrentDerivedCredential = v14;
    if ( !v14 )
      return 0;
    v15 = 502;
    v16 = v14;
LABEL_11:
    DebugTraceError(v16, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", v15);
    return CurrentDerivedCredential;
  }
  if ( CurrentDerivedCredential )
  {
    v15 = 508;
    v16 = CurrentDerivedCredential;
    goto LABEL_11;
  }
  return 0;
}

```

## disassembly

```asm
0x180012710  mov     rax, rsp
0x180012713  push    rbx
0x180012714  push    rbp
0x180012715  push    rsi
0x180012716  push    rdi
0x180012717  push    r12
0x180012719  push    r13
0x18001271b  push    r14
0x18001271d  push    r15
0x18001271f  sub     rsp, 48h
0x180012723  mov     r14, [rsp+88h+arg_38]
0x18001272b  mov     esi, r9d
0x18001272e  mov     r15, [rsp+88h+arg_30]
0x180012736  mov     rbp, rdx
0x180012739  mov     r12d, [rsp+88h+arg_28]
0x180012741  mov     r13, [rsp+88h+arg_20]
0x180012749  mov     [rax-50h], r14
0x18001274d  mov     [rax-58h], r15
0x180012751  mov     [rax-60h], r12d
0x180012755  mov     [rax-68h], r13
0x180012759  call    ?RetrieveCurrentDerivedCredential@@YAKHPEAU_LUID@@PEAU_GUID@@HPEAEKQEAEPEAK@Z; RetrieveCurrentDerivedCredential(int,_LUID *,_GUID *,int,uchar *,ulong,uchar * const,ulong *)
0x18001275e  mov     ecx, 0C000090Ch; Status
0x180012763  mov     ebx, eax
0x180012765  call    cs:__imp_RtlNtStatusToDosError
0x18001276c  nop     dword ptr [rax+rax+00h]
0x180012771  cmp     ebx, eax
0x180012773  jz      short loc_180012793
0x180012775  test    ebx, ebx
0x180012777  jnz     loc_180012812
0x18001277d  xor     ebx, ebx
0x18001277f  mov     eax, ebx
0x180012781  add     rsp, 48h
0x180012785  pop     r15
0x180012787  pop     r14
0x180012789  pop     r13
0x18001278b  pop     r12
0x18001278d  pop     rdi
0x18001278e  pop     rsi
0x18001278f  pop     rbp
0x180012790  pop     rbx
0x180012791  retn
0x180012793  mov     rcx, cs:WPP_GLOBAL_Control; int
0x18001279a  lea     rax, WPP_GLOBAL_Control
0x1800127a1  lea     rdi, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800127a8  cmp     rcx, rax
0x1800127ab  jz      short loc_1800127B3
0x1800127ad  test    byte ptr [rcx+1Ch], 1
0x1800127b1  jnz     short loc_1800127E8
0x1800127b3  mov     [rsp+88h+var_50], r14; unsigned int *
0x1800127b8  mov     r9d, esi; int
0x1800127bb  mov     [rsp+88h+var_58], r15; unsigned __int8 *
0x1800127c0  xor     r8d, r8d; struct _GUID *
0x1800127c3  mov     [rsp+88h+cbInput], r12d; cbInput
0x1800127c8  mov     rdx, rbp; struct _LUID *
0x1800127cb  mov     [rsp+88h+var_68], r13; unsigned __int8 *
0x1800127d0  call    ?RetrieveCurrentDerivedCredential@@YAKHPEAU_LUID@@PEAU_GUID@@HPEAEKQEAEPEAK@Z; RetrieveCurrentDerivedCredential(int,_LUID *,_GUID *,int,uchar *,ulong,uchar * const,ulong *)
0x1800127d5  mov     ebx, eax
0x1800127d7  test    eax, eax
0x1800127d9  jz      short loc_18001277D
0x1800127db  mov     r9d, 1F6h
0x1800127e1  mov     r8, rdi
0x1800127e4  mov     ecx, eax
0x1800127e6  jmp     short loc_180012821
0x1800127e8  mov     rcx, [rcx+10h]
0x1800127ec  lea     r9, aDwerror; "dwError"
0x1800127f3  mov     dword ptr [rsp+88h+var_58], 1E8h
0x1800127fb  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x180012802  mov     qword ptr [rsp+88h+cbInput], rdi
0x180012807  mov     dword ptr [rsp+88h+var_68], ebx
0x18001280b  call    WPP_SF_sDsd
0x180012810  jmp     short loc_1800127B3
0x180012812  mov     r9d, 1FCh
0x180012818  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18001281f  mov     ecx, ebx
0x180012821  lea     rdx, aDwerror; "dwError"
0x180012828  call    DebugTraceError
0x18001282d  jmp     loc_18001277F
```
