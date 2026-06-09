# LdrpProcessWork

- ea: `0x180025698`
- end: `0x18002585b`
- name: `LdrpProcessWork`
- size: `451`
- prototype: `__int64 __fastcall(char ArgList)`
- caller_count: `4`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800249a0`
- `0x1800254e0`
- `0x180025870`
- `0x180119f5c`

## callees

- `0x18001eb80`
- `0x180025698`
- `0x180027a20`
- `0x180041690`
- `0x1800535c0`
- `0x180053ab0`
- `0x1800ac3d0`
- `0x1800acb14`
- `0x1800be2e0`
- `0x1800d4320`
- `0x1800d9288`
- `0x1800f7704`
- `0x18010d7f4`
- `0x18015e490`

## string_xrefs

- `0x180025752`: `Unable to load DLL: "%wZ", Parent Module: "%wZ", Status: 0x%x\n`

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
0x180025698  mov     rax, rsp
0x18002569b  mov     [rax+18h], rbx
0x18002569f  mov     [rax+20h], rsi
0x1800256a3  mov     [rax+10h], dl
0x1800256a6  mov     [rax+8], rcx
0x1800256aa  push    rdi
0x1800256ab  sub     rsp, 40h
0x1800256af  mov     sil, dl
0x1800256b2  mov     rbx, rcx
0x1800256b5  mov     rax, [rcx+28h]
0x1800256b9  mov     ecx, [rax]
0x1800256bb  test    ecx, ecx
0x1800256bd  js      loc_1800257F2
0x1800256c3  mov     rax, [rbx+38h]
0x1800256c7  mov     rcx, [rax+98h]
0x1800256ce  mov     eax, [rcx+38h]
0x1800256d1  mov     rcx, rbx
0x1800256d4  test    eax, eax
0x1800256d6  jnz     loc_1800257E1
0x1800256dc  mov     rax, [rbx+38h]
0x1800256e0  cmp     dword ptr [rax+10Ch], 9
0x1800256e7  jnz     short loc_1800256F0
0x1800256e9  call    LdrpMapDllPatchImage
0x1800256ee  jmp     short loc_180025715
0x1800256f0  test    dword ptr [rbx+20h], 100000h
0x1800256f7  jz      short loc_180025700
0x1800256f9  call    LdrpMapDllRetry
0x1800256fe  jmp     short loc_180025715
0x180025700  test    dword ptr [rbx+20h], 200h
0x180025707  jz      short loc_180025710
0x180025709  call    LdrpMapDllFullPath
0x18002570e  jmp     short loc_180025715
0x180025710  call    LdrpMapDllSearchPath
0x180025715  mov     edi, eax
0x180025717  mov     ecx, 80000000h
0x18002571c  lea     eax, [rax+rcx]
0x18002571f  test    ecx, eax
0x180025721  jnz     loc_1800257F2
0x180025727  cmp     edi, 0C000022Dh
0x18002572d  jz      loc_1800257F2
0x180025733  mov     rax, [rbx+30h]
0x180025737  lea     rcx, [rax+48h]
0x18002573b  neg     rax
0x18002573e  sbb     rdx, rdx
0x180025741  and     rdx, rcx
0x180025744  mov     [rsp+48h+var_10], edi
0x180025748  mov     [rsp+48h+var_18], rdx
0x18002574d  mov     qword ptr [rsp+48h+ArgList], rbx; ArgList
0x180025752  lea     rax, aUnableToLoadDl; "Unable to load DLL: \"%wZ\", Parent Mod"...
0x180025759  mov     [rsp+48h+Format], rax; Format
0x18002575e  xor     r9d, r9d; int
0x180025761  lea     r8, aLdrpprocesswor; "LdrpProcessWork"
0x180025768  mov     edx, 8A4h; int
0x18002576d  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x180025774  call    LdrpLogInternal
0x180025779  cmp     edi, 0C0000135h
0x18002577f  jnz     short loc_1800257E8
0x180025781  mov     edx, 19h
0x180025786  mov     r9, rbx
0x180025789  xor     r8d, r8d
0x18002578c  mov     ecx, edi
0x18002578e  call    LdrpLogError
0x180025793  mov     rcx, rbx
0x180025796  call    LdrpLogDeprecatedDllEtwEvent
0x18002579b  mov     rax, [rbx+30h]
0x18002579f  lea     rcx, [rax+48h]
0x1800257a3  neg     rax
0x1800257a6  sbb     rdx, rdx
0x1800257a9  and     rdx, rcx
0x1800257ac  mov     byte ptr [rsp+48h+Format], 0
0x1800257b1  lea     r9, LoadFailure
0x1800257b8  mov     r8d, 0C0000135h
0x1800257be  mov     rcx, rbx
0x1800257c1  call    LdrpLogLoadFailureEtwEvent
0x1800257c6  mov     rax, [rbx+38h]
0x1800257ca  mov     ecx, [rax+68h]
0x1800257cd  test    cl, 20h
0x1800257d0  jz      short loc_1800257E8
0x1800257d2  xor     edx, edx
0x1800257d4  mov     r8d, edi
0x1800257d7  mov     rcx, rbx
0x1800257da  call    LdrpReportError
0x1800257df  jmp     short loc_1800257E8
0x1800257e1  call    LdrpSnapModule
0x1800257e6  mov     edi, eax
0x1800257e8  test    edi, edi
0x1800257ea  jns     short loc_1800257F2
0x1800257ec  mov     rax, [rbx+28h]
0x1800257f0  mov     [rax], edi
0x1800257f2  test    sil, sil
0x1800257f5  jnz     short loc_18002584A
0x1800257f7  lea     rcx, LdrpWorkQueueLock
0x1800257fe  call    RtlEnterCriticalSection
0x180025803  mov     eax, cs:LdrpWorkInProgress
0x180025809  dec     eax
0x18002580b  mov     cs:LdrpWorkInProgress, eax
0x180025811  lea     rcx, LdrpWorkQueue
0x180025818  cmp     cs:LdrpWorkQueue, rcx
0x18002581f  jnz     short loc_18002582A
0x180025821  mov     ebx, 1
0x180025826  cmp     eax, ebx
0x180025828  jz      short loc_18002582C
0x18002582a  xor     bl, bl
0x18002582c  lea     rcx, LdrpWorkQueueLock
0x180025833  call    RtlLeaveCriticalSection
0x180025838  test    bl, bl
0x18002583a  jz      short loc_18002584A
0x18002583c  xor     edx, edx
0x18002583e  mov     rcx, cs:LdrpWorkCompleteEvent
0x180025845  call    ZwSetEvent
0x18002584a  mov     rbx, [rsp+48h+arg_10]
0x18002584f  mov     rsi, [rsp+48h+arg_18]
0x180025854  add     rsp, 40h
0x180025858  pop     rdi
0x180025859  retn
0x18016582b  push    rbx
0x18016582d  push    rbp
0x18016582e  sub     rsp, 48h
0x180165832  mov     rbp, rdx
0x180165835  test    cl, cl
0x180165837  jz      short loc_18016585A
0x180165839  mov     r9, [rbp+50h]
0x18016583d  mov     rax, [r9+28h]
0x180165841  mov     dword ptr [rax], 0C0000005h
0x180165847  mov     edx, 14ABh
0x18016584c  xor     r8d, r8d
0x18016584f  mov     ecx, 0C0000005h
0x180165854  call    LdrpLogError
0x180165859  nop
0x18016585a  cmp     byte ptr [rbp+58h], 0
0x18016585e  jnz     short loc_1801658B4
0x180165860  lea     rcx, LdrpWorkQueueLock
0x180165867  call    RtlEnterCriticalSection
0x18016586c  mov     eax, cs:LdrpWorkInProgress
0x180165872  dec     eax
0x180165874  mov     cs:LdrpWorkInProgress, eax
0x18016587a  lea     rcx, LdrpWorkQueue
0x180165881  cmp     cs:LdrpWorkQueue, rcx
0x180165888  jnz     short loc_180165893
0x18016588a  cmp     eax, 1
0x18016588d  jnz     short loc_180165893
0x18016588f  mov     ebx, eax
0x180165891  jmp     short loc_180165895
0x180165893  xor     ebx, ebx
0x180165895  lea     rcx, LdrpWorkQueueLock
0x18016589c  call    RtlLeaveCriticalSection
0x1801658a1  test    bl, bl
0x1801658a3  jz      short loc_1801658B4
0x1801658a5  xor     edx, edx
0x1801658a7  mov     rcx, cs:LdrpWorkCompleteEvent
0x1801658ae  call    ZwSetEvent
0x1801658b3  nop
0x1801658b4  add     rsp, 48h
0x1801658b8  pop     rbp
0x1801658b9  pop     rbx
0x1801658ba  retn
```
