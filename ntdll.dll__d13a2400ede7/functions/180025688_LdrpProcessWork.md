# LdrpProcessWork

- ea: `0x180025688`
- end: `0x18002584b`
- name: `LdrpProcessWork`
- size: `451`
- prototype: `__int64 __fastcall(char ArgList)`
- caller_count: `4`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180024990`
- `0x1800254d0`
- `0x180025860`
- `0x18011aa4c`

## callees

- `0x18001eb80`
- `0x180025688`
- `0x180027910`
- `0x1800376a0`
- `0x18004f1dc`
- `0x18006ffa0`
- `0x180070490`
- `0x1800b6f08`
- `0x1800b7654`
- `0x1800c25c0`
- `0x1800d9d08`
- `0x1800f81e4`
- `0x18010eb44`
- `0x18015eca0`

## string_xrefs

- `0x180025742`: `Unable to load DLL: "%wZ", Parent Module: "%wZ", Status: 0x%x\n`

## pseudocode

```c
void __fastcall LdrpProcessWork(__int64 ArgList, char a2)
{
  int v4; // eax
  int v5; // edi
  int v6; // eax
  char v7; // bl

  if ( **(int **)(ArgList + 40) < 0 )
    goto LABEL_18;
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(ArgList + 56) + 152LL) + 56LL) )
  {
    v5 = LdrpSnapModule(ArgList);
  }
  else
  {
    if ( *(_DWORD *)(*(_QWORD *)(ArgList + 56) + 268LL) == 9 )
    {
      v4 = LdrpMapDllPatchImage(ArgList);
    }
    else if ( (*(_DWORD *)(ArgList + 32) & 0x100000) != 0 )
    {
      v4 = LdrpMapDllRetry(ArgList);
    }
    else if ( (*(_DWORD *)(ArgList + 32) & 0x200) != 0 )
    {
      v4 = LdrpMapDllFullPath(ArgList);
    }
    else
    {
      v4 = LdrpMapDllSearchPath(ArgList);
    }
    v5 = v4;
    if ( (int)(v4 + 0x80000000) < 0 || v4 == -1073741267 )
      goto LABEL_18;
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrmap.c",
      2212,
      (int)"LdrpProcessWork",
      0,
      "Unable to load DLL: \"%wZ\", Parent Module: \"%wZ\", Status: 0x%x\n",
      ArgList);
    if ( v5 == -1073741515 )
    {
      LdrpLogError(3221225781LL, 25, 0, ArgList);
      LdrpLogDeprecatedDllEtwEvent(ArgList);
      LdrpLogLoadFailureEtwEvent(
        ArgList,
        (*(_DWORD *)(ArgList + 48) + 72) & ((unsigned __int128)-(__int128)*(unsigned __int64 *)(ArgList + 48) >> 64),
        -1073741515,
        (unsigned int)LoadFailure,
        0);
      if ( (*(_DWORD *)(*(_QWORD *)(ArgList + 56) + 104LL) & 0x20) != 0 )
        LdrpReportError((__int128 *)ArgList, 0, 0xC0000135);
    }
  }
  if ( v5 < 0 )
    **(_DWORD **)(ArgList + 40) = v5;
LABEL_18:
  if ( !a2 )
  {
    RtlEnterCriticalSection(&LdrpWorkQueueLock);
    v6 = --LdrpWorkInProgress;
    if ( (__int64 *)LdrpWorkQueue != &LdrpWorkQueue || (v7 = 1, v6 != 1) )
      v7 = 0;
    RtlLeaveCriticalSection(&LdrpWorkQueueLock);
    if ( v7 )
      ZwSetEvent(LdrpWorkCompleteEvent, 0);
  }
}

```

## disassembly

```asm
0x180025688  mov     rax, rsp
0x18002568b  mov     [rax+18h], rbx
0x18002568f  mov     [rax+20h], rsi
0x180025693  mov     [rax+10h], dl
0x180025696  mov     [rax+8], rcx
0x18002569a  push    rdi
0x18002569b  sub     rsp, 40h
0x18002569f  mov     sil, dl
0x1800256a2  mov     rbx, rcx
0x1800256a5  mov     rax, [rcx+28h]
0x1800256a9  mov     ecx, [rax]
0x1800256ab  test    ecx, ecx
0x1800256ad  js      loc_1800257E2
0x1800256b3  mov     rax, [rbx+38h]
0x1800256b7  mov     rcx, [rax+98h]
0x1800256be  mov     eax, [rcx+38h]
0x1800256c1  mov     rcx, rbx
0x1800256c4  test    eax, eax
0x1800256c6  jnz     loc_1800257D1
0x1800256cc  mov     rax, [rbx+38h]
0x1800256d0  cmp     dword ptr [rax+10Ch], 9
0x1800256d7  jnz     short loc_1800256E0
0x1800256d9  call    LdrpMapDllPatchImage
0x1800256de  jmp     short loc_180025705
0x1800256e0  test    dword ptr [rbx+20h], 100000h
0x1800256e7  jz      short loc_1800256F0
0x1800256e9  call    LdrpMapDllRetry
0x1800256ee  jmp     short loc_180025705
0x1800256f0  test    dword ptr [rbx+20h], 200h
0x1800256f7  jz      short loc_180025700
0x1800256f9  call    LdrpMapDllFullPath
0x1800256fe  jmp     short loc_180025705
0x180025700  call    LdrpMapDllSearchPath
0x180025705  mov     edi, eax
0x180025707  mov     ecx, 80000000h
0x18002570c  lea     eax, [rax+rcx]
0x18002570f  test    ecx, eax
0x180025711  jnz     loc_1800257E2
0x180025717  cmp     edi, 0C000022Dh
0x18002571d  jz      loc_1800257E2
0x180025723  mov     rax, [rbx+30h]
0x180025727  lea     rcx, [rax+48h]
0x18002572b  neg     rax
0x18002572e  sbb     rdx, rdx
0x180025731  and     rdx, rcx
0x180025734  mov     [rsp+48h+var_10], edi
0x180025738  mov     [rsp+48h+var_18], rdx
0x18002573d  mov     qword ptr [rsp+48h+ArgList], rbx; ArgList
0x180025742  lea     rax, aUnableToLoadDl; "Unable to load DLL: \"%wZ\", Parent Mod"...
0x180025749  mov     [rsp+48h+Format], rax; Format
0x18002574e  xor     r9d, r9d; int
0x180025751  lea     r8, aLdrpprocesswor; "LdrpProcessWork"
0x180025758  mov     edx, 8A4h; int
0x18002575d  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x180025764  call    LdrpLogInternal
0x180025769  cmp     edi, 0C0000135h
0x18002576f  jnz     short loc_1800257D8
0x180025771  mov     edx, 19h
0x180025776  mov     r9, rbx
0x180025779  xor     r8d, r8d
0x18002577c  mov     ecx, edi
0x18002577e  call    LdrpLogError
0x180025783  mov     rcx, rbx
0x180025786  call    LdrpLogDeprecatedDllEtwEvent
0x18002578b  mov     rax, [rbx+30h]
0x18002578f  lea     rcx, [rax+48h]
0x180025793  neg     rax
0x180025796  sbb     rdx, rdx
0x180025799  and     rdx, rcx
0x18002579c  mov     byte ptr [rsp+48h+Format], 0
0x1800257a1  lea     r9, LoadFailure
0x1800257a8  mov     r8d, 0C0000135h
0x1800257ae  mov     rcx, rbx
0x1800257b1  call    LdrpLogLoadFailureEtwEvent
0x1800257b6  mov     rax, [rbx+38h]
0x1800257ba  mov     ecx, [rax+68h]
0x1800257bd  test    cl, 20h
0x1800257c0  jz      short loc_1800257D8
0x1800257c2  xor     edx, edx
0x1800257c4  mov     r8d, edi
0x1800257c7  mov     rcx, rbx
0x1800257ca  call    LdrpReportError
0x1800257cf  jmp     short loc_1800257D8
0x1800257d1  call    LdrpSnapModule
0x1800257d6  mov     edi, eax
0x1800257d8  test    edi, edi
0x1800257da  jns     short loc_1800257E2
0x1800257dc  mov     rax, [rbx+28h]
0x1800257e0  mov     [rax], edi
0x1800257e2  test    sil, sil
0x1800257e5  jnz     short loc_18002583A
0x1800257e7  lea     rcx, LdrpWorkQueueLock
0x1800257ee  call    RtlEnterCriticalSection
0x1800257f3  mov     eax, cs:LdrpWorkInProgress
0x1800257f9  dec     eax
0x1800257fb  mov     cs:LdrpWorkInProgress, eax
0x180025801  lea     rcx, LdrpWorkQueue
0x180025808  cmp     cs:LdrpWorkQueue, rcx
0x18002580f  jnz     short loc_18002581A
0x180025811  mov     ebx, 1
0x180025816  cmp     eax, ebx
0x180025818  jz      short loc_18002581C
0x18002581a  xor     bl, bl
0x18002581c  lea     rcx, LdrpWorkQueueLock
0x180025823  call    RtlLeaveCriticalSection
0x180025828  test    bl, bl
0x18002582a  jz      short loc_18002583A
0x18002582c  xor     edx, edx
0x18002582e  mov     rcx, cs:LdrpWorkCompleteEvent
0x180025835  call    ZwSetEvent
0x18002583a  mov     rbx, [rsp+48h+arg_10]
0x18002583f  mov     rsi, [rsp+48h+arg_18]
0x180025844  add     rsp, 40h
0x180025848  pop     rdi
0x180025849  retn
0x18016602b  push    rbx
0x18016602d  push    rbp
0x18016602e  sub     rsp, 48h
0x180166032  mov     rbp, rdx
0x180166035  test    cl, cl
0x180166037  jz      short loc_18016605A
0x180166039  mov     r9, [rbp+50h]
0x18016603d  mov     rax, [r9+28h]
0x180166041  mov     dword ptr [rax], 0C0000005h
0x180166047  mov     edx, 14ABh
0x18016604c  xor     r8d, r8d
0x18016604f  mov     ecx, 0C0000005h
0x180166054  call    LdrpLogError
0x180166059  nop
0x18016605a  cmp     byte ptr [rbp+58h], 0
0x18016605e  jnz     short loc_1801660B4
0x180166060  lea     rcx, LdrpWorkQueueLock
0x180166067  call    RtlEnterCriticalSection
0x18016606c  mov     eax, cs:LdrpWorkInProgress
0x180166072  dec     eax
0x180166074  mov     cs:LdrpWorkInProgress, eax
0x18016607a  lea     rcx, LdrpWorkQueue
0x180166081  cmp     cs:LdrpWorkQueue, rcx
0x180166088  jnz     short loc_180166093
0x18016608a  cmp     eax, 1
0x18016608d  jnz     short loc_180166093
0x18016608f  mov     ebx, eax
0x180166091  jmp     short loc_180166095
0x180166093  xor     ebx, ebx
0x180166095  lea     rcx, LdrpWorkQueueLock
0x18016609c  call    RtlLeaveCriticalSection
0x1801660a1  test    bl, bl
0x1801660a3  jz      short loc_1801660B4
0x1801660a5  xor     edx, edx
0x1801660a7  mov     rcx, cs:LdrpWorkCompleteEvent
0x1801660ae  call    ZwSetEvent
0x1801660b3  nop
0x1801660b4  add     rsp, 48h
0x1801660b8  pop     rbp
0x1801660b9  pop     rbx
0x1801660ba  retn
```
