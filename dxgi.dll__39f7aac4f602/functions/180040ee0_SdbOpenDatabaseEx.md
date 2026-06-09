# SdbOpenDatabaseEx

- ea: `0x180040ee0`
- end: `0x180041247`
- name: `SdbOpenDatabaseEx`
- size: `871`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a77cc`
- `0x1800a7bd4`

## callees

- `0x180040ee0`
- `0x180041774`
- `0x180042794`
- `0x18004281c`
- `0x1800614b8`
- `0x18006b1c8`
- `0x1800710a8`
- `0x180075fa0`
- `0x180076f20`
- `0x1800ab848`
- `0x1800adcc8`
- `0x1800c0dac`
- `0x1800c0e28`
- `0x1800c12b8`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180040f6b`
- `ntdll!RtlAllocateHeap` at `0x180040f6b`

## string_xrefs

- `0x180040f25`: `SdbOpenDatabaseEx`
- `0x180040f8a`: `SdbOpenDatabaseEx`
- `0x18004101f`: `SdbOpenDatabaseEx`
- `0x18004105c`: `SdbOpenDatabaseEx`
- `0x180041088`: `SdbOpenDatabaseEx`
- `0x1800410df`: `SdbOpenDatabaseEx`
- `0x1800411b1`: `SdbOpenDatabaseEx`
- `0x1800411f0`: `SdbOpenDatabaseEx`
- `0x180040f0a`: `Flags:%d; DatabasePath:%ws`
- `0x180041076`: `SdbGetMergeRedirectPath failed to check for sdb merge redirect [%x]`
- `0x1800410d2`: `Failed to create file mapping [%x]`
- `0x18004104b`: `Failed to create file mapping for redirected SDB file [%x]`
- `0x1800411e3`: `Failed to open SDB - File size too large or small.`
- `0x180041153`: `Failed to read database header`
- `0x1800411a4`: `SdbpOpenCompressedDatabase failed to open compressed database.`

## pseudocode

```c
_QWORD *__fastcall SdbOpenDatabaseEx(int *a1, __int64 a2, unsigned int a3)
{
  int *v5; // rax
  _QWORD *Heap; // rax
  _QWORD *v7; // rbx
  int MergeRedirectPath; // eax
  int v9; // r14d
  int v10; // esi
  const wchar_t *FileNamePart; // rax
  int v12; // eax
  int v13; // eax
  const char *v14; // r9
  __int64 v15; // r8
  __int64 v16; // rsi
  __int64 v17; // rdx
  __int64 v19; // [rsp+20h] [rbp-40h]
  int v20; // [rsp+30h] [rbp-30h] BYREF
  __int64 v21; // [rsp+38h] [rbp-28h] BYREF
  _QWORD *v22; // [rsp+40h] [rbp-20h] BYREF
  __int64 v23; // [rsp+48h] [rbp-18h] BYREF
  int v24; // [rsp+50h] [rbp-10h]

  v23 = 0;
  v24 = 0;
  v20 = 0;
  v5 = a1;
  if ( !a1 )
    v5 = &dword_1800D7C24;
  AslLogCallPrintf(3, "SdbOpenDatabaseEx", 2501, "Flags:%d; DatabasePath:%ws", a3, v5);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xA80u);
  v22 = Heap;
  v7 = Heap;
  if ( Heap )
  {
    memset_0(Heap, 0, 0xA80u);
    v21 = 0;
    if ( (a3 & 0x10) != 0 )
      goto LABEL_47;
    MergeRedirectPath = SdbGetMergeRedirectPath(&v21, &v20, (a3 & 0x20) == 0, a1);
    v9 = MergeRedirectPath;
    if ( MergeRedirectPath < 0 )
    {
      if ( MergeRedirectPath != -1073741772 )
        AslLogCallPrintf(
          3,
          "SdbOpenDatabaseEx",
          2527,
          "SdbGetMergeRedirectPath failed to check for sdb merge redirect [%x]",
          MergeRedirectPath);
      v10 = v9;
    }
    else if ( v21 )
    {
      if ( (a3 & 0x20) != 0 )
      {
        if ( !v20 )
          *((_DWORD *)v7 + 6) |= 0x20u;
      }
      else if ( v20 )
      {
        FileNamePart = (const wchar_t *)AslPathGetFileNamePart(a1);
        AslLogCallPrintf(
          1,
          "SdbOpenDatabaseEx",
          2539,
          "Handled Error: MergeSdb staged deletion feature was used to prevent sdb mismatch error. SdbName: [%ls].",
          FileNamePart);
      }
      v12 = AslFileMappingCreate(v7, v21);
      v10 = v12;
      if ( v12 < 0 )
        AslLogCallPrintf(
          1,
          "SdbOpenDatabaseEx",
          2558,
          "Failed to create file mapping for redirected SDB file [%x]",
          v12);
    }
    else
    {
      v10 = -1073741772;
    }
    if ( v21 )
      AslFree(NtCurrentPeb()->ProcessHeap, v21);
    if ( v10 < 0 || !*v7 )
    {
LABEL_47:
      v13 = AslFileMappingCreate(v7, a1);
      if ( v13 < 0 )
      {
        v14 = "Failed to create file mapping [%x]";
        v15 = 2580;
LABEL_25:
        LODWORD(v19) = v13;
        AslLogCallPrintf(1, "SdbOpenDatabaseEx", v15, v14, v19);
        goto LABEL_42;
      }
    }
    v16 = *(_QWORD *)(*v7 + 24LL);
    if ( (unsigned __int64)(v16 - 42) > 0xFFFFFD5 )
    {
      AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2589, "Failed to open SDB - File size too large or small.");
      goto LABEL_42;
    }
    v13 = AslFileMappingEnsureMappedAsEx();
    if ( v13 < 0 )
    {
      v14 = "Failed to map SDB [%x]";
      v15 = 2595;
      goto LABEL_25;
    }
    *((_DWORD *)v7 + 4) = 0;
    *((_DWORD *)v7 + 5) = v16;
    v7[1] = AslFileMappingGetViewBase(*v7);
    if ( !(unsigned int)SdbpReadMappedData(v7, 0, &v23, 12) )
    {
      AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2608, "Failed to read database header");
      goto LABEL_42;
    }
    v13 = v24;
    if ( v24 != 1717724275 )
    {
      if ( v24 == 1717724282 )
      {
        if ( (unsigned int)SdbpOpenCompressedDatabase(&v22, v17, a3) )
          return v22;
        AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2627, "SdbpOpenCompressedDatabase failed to open compressed database.");
        v7 = v22;
LABEL_42:
        if ( v7 )
        {
          AslFileMappingDelete(*v7);
          AslFree(NtCurrentPeb()->ProcessHeap, v7);
        }
        return 0;
      }
      if ( (a3 & 2) == 0 )
      {
        v14 = "Magic does not match a valid value: 0x%lx";
        v15 = 2621;
        goto LABEL_25;
      }
    }
    if ( (unsigned int)SdbpValidateAndApplyCompatFlags(v7, &v23, a3) )
      return v7;
    goto LABEL_42;
  }
  AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2509, "Failed to allocate DB structure");
  return 0;
}

```

## disassembly

```asm
0x180040ee0  mov     r11, rsp
0x180040ee3  mov     [r11+10h], rbx
0x180040ee7  mov     [r11+20h], rsi
0x180040eeb  push    rbp
0x180040eec  push    rdi
0x180040eed  push    r12
0x180040eef  push    r13
0x180040ef1  push    r14
0x180040ef3  mov     rbp, rsp
0x180040ef6  sub     rsp, 60h
0x180040efa  mov     rax, cs:__security_cookie
0x180040f01  xor     rax, rsp
0x180040f04  mov     [rbp+var_8], rax
0x180040f08  xor     eax, eax
0x180040f0a  lea     r9, aFlagsDDatabase; "Flags:%d; DatabasePath:%ws"
0x180040f11  mov     r13, rcx
0x180040f14  mov     [rbp+var_18], rax
0x180040f18  mov     [rbp+var_10], eax
0x180040f1b  lea     rcx, dword_1800D7C24
0x180040f22  mov     [rbp+var_30], eax
0x180040f25  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x180040f2c  mov     r12d, r8d
0x180040f2f  test    r13, r13
0x180040f32  mov     rax, r13
0x180040f35  cmovz   rax, rcx
0x180040f39  mov     ecx, 3
0x180040f3e  mov     [r11-60h], rax
0x180040f42  mov     [r11-68h], r8d
0x180040f46  mov     r8d, 9C5h
0x180040f4c  call    AslLogCallPrintf
0x180040f51  mov     rcx, gs:60h
0x180040f5a  mov     edi, 0A80h
0x180040f5f  mov     r8d, edi; Size
0x180040f62  mov     edx, 8; Flags
0x180040f67  mov     rcx, [rcx+30h]; HeapHandle
0x180040f6b  call    cs:__imp_RtlAllocateHeap
0x180040f71  mov     [rbp+var_20], rax
0x180040f75  mov     rbx, rax
0x180040f78  test    rax, rax
0x180040f7b  jnz     short loc_180040F9E
0x180040f7d  lea     r9, aFailedToAlloca_10; "Failed to allocate DB structure"
0x180040f84  mov     r8d, 9CDh
0x180040f8a  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x180040f91  lea     ecx, [rax+1]
0x180040f94  call    AslLogCallPrintf
0x180040f99  jmp     loc_180041220
0x180040f9e  mov     r8, rdi; Size
0x180040fa1  xor     edx, edx; Val
0x180040fa3  mov     rcx, rbx; void *
0x180040fa6  call    memset_0
0x180040fab  mov     [rbp+var_28], 0
0x180040fb3  mov     edi, 1
0x180040fb8  test    r12b, 10h
0x180040fbc  jnz     loc_1800410C3
0x180040fc2  lea     r8d, [rdi-1]
0x180040fc6  mov     esi, r12d
0x180040fc9  and     esi, 20h
0x180040fcc  lea     rdx, [rbp+var_30]
0x180040fd0  mov     r9, r13
0x180040fd3  lea     rcx, [rbp+var_28]
0x180040fd7  setz    r8b
0x180040fdb  call    SdbGetMergeRedirectPath
0x180040fe0  mov     r14d, eax
0x180040fe3  test    eax, eax
0x180040fe5  js      loc_18004106C
0x180040feb  cmp     [rbp+var_28], 0
0x180040ff0  jnz     short loc_180040FFC
0x180040ff2  mov     esi, 0C0000034h
0x180040ff7  jmp     loc_18004109C
0x180040ffc  test    esi, esi
0x180040ffe  jnz     short loc_18004102F
0x180041000  cmp     [rbp+var_30], esi
0x180041003  jz      short loc_180041039
0x180041005  mov     rcx, r13
0x180041008  call    AslPathGetFileNamePart
0x18004100d  lea     r9, aHandledErrorMe; "Handled Error: MergeSdb staged deletion"...
0x180041014  mov     [rsp+60h+var_40], rax
0x180041019  mov     r8d, 9EBh
0x18004101f  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x180041026  mov     ecx, edi
0x180041028  call    AslLogCallPrintf
0x18004102d  jmp     short loc_180041039
0x18004102f  cmp     [rbp+var_30], 0
0x180041033  jnz     short loc_180041039
0x180041035  or      dword ptr [rbx+18h], 20h
0x180041039  mov     rdx, [rbp+var_28]
0x18004103d  mov     rcx, rbx
0x180041040  call    AslFileMappingCreate
0x180041045  mov     esi, eax
0x180041047  test    eax, eax
0x180041049  jns     short loc_18004109C
0x18004104b  lea     r9, aFailedToCreate_3; "Failed to create file mapping for redir"...
0x180041052  mov     dword ptr [rsp+60h+var_40], eax
0x180041056  mov     r8d, 9FEh
0x18004105c  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x180041063  mov     ecx, edi
0x180041065  call    AslLogCallPrintf
0x18004106a  jmp     short loc_18004109C
0x18004106c  mov     esi, 0C0000034h
0x180041071  cmp     r14d, esi
0x180041074  jz      short loc_180041099
0x180041076  lea     r9, aSdbgetmergered; "SdbGetMergeRedirectPath failed to check"...
0x18004107d  mov     dword ptr [rsp+60h+var_40], r14d
0x180041082  mov     r8d, 9DFh
0x180041088  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x18004108f  mov     ecx, 3
0x180041094  call    AslLogCallPrintf
0x180041099  mov     esi, r14d
0x18004109c  cmp     [rbp+var_28], 0
0x1800410a1  jz      short loc_1800410B9
0x1800410a3  mov     rcx, gs:60h
0x1800410ac  mov     rdx, [rbp+var_28]
0x1800410b0  mov     rcx, [rcx+30h]
0x1800410b4  call    AslFree
0x1800410b9  test    esi, esi
0x1800410bb  js      short loc_1800410C3
0x1800410bd  cmp     qword ptr [rbx], 0
0x1800410c1  jnz     short loc_1800410F6
0x1800410c3  mov     rdx, r13
0x1800410c6  mov     rcx, rbx
0x1800410c9  call    AslFileMappingCreate
0x1800410ce  test    eax, eax
0x1800410d0  jns     short loc_1800410F6
0x1800410d2  lea     r9, aFailedToCreate_0; "Failed to create file mapping [%x]"
0x1800410d9  mov     r8d, 0A14h
0x1800410df  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x1800410e6  mov     dword ptr [rsp+60h+var_40], eax
0x1800410ea  mov     ecx, edi
0x1800410ec  call    AslLogCallPrintf
0x1800410f1  jmp     loc_1800411FE
0x1800410f6  mov     rcx, [rbx]
0x1800410f9  mov     rsi, [rcx+18h]
0x1800410fd  lea     rax, [rsi-2Ah]
0x180041101  cmp     rax, 0FFFFFD5h
0x180041107  ja      loc_1800411E3
0x18004110d  call    AslFileMappingEnsureMappedAsEx
0x180041112  test    eax, eax
0x180041114  jns     short loc_180041125
0x180041116  lea     r9, aFailedToMapSdb; "Failed to map SDB [%x]"
0x18004111d  mov     r8d, 0A23h
0x180041123  jmp     short loc_1800410DF
0x180041125  mov     dword ptr [rbx+10h], 0
0x18004112c  mov     [rbx+14h], esi
0x18004112f  mov     rcx, [rbx]
0x180041132  call    AslFileMappingGetViewBase
0x180041137  mov     r9d, 0Ch
0x18004113d  mov     [rbx+8], rax
0x180041141  lea     r8, [rbp+var_18]
0x180041145  xor     edx, edx
0x180041147  mov     rcx, rbx
0x18004114a  call    SdbpReadMappedData
0x18004114f  test    eax, eax
0x180041151  jnz     short loc_180041165
0x180041153  lea     r9, aFailedToReadDa_0; "Failed to read database header"
0x18004115a  mov     r8d, 0A30h
0x180041160  jmp     loc_1800411F0
0x180041165  mov     eax, [rbp+var_10]
0x180041168  mov     ecx, 6662647Ah
0x18004116d  cmp     eax, 66626473h
0x180041172  jz      short loc_180041190
0x180041174  cmp     eax, ecx
0x180041176  jz      short loc_180041194
0x180041178  test    r12b, 2
0x18004117c  jnz     short loc_180041190
0x18004117e  lea     r9, aMagicDoesNotMa_0; "Magic does not match a valid value: 0x%"...
0x180041185  mov     r8d, 0A3Dh
0x18004118b  jmp     loc_1800410DF
0x180041190  cmp     eax, ecx
0x180041192  jnz     short loc_1800411CB
0x180041194  mov     r8d, r12d
0x180041197  lea     rcx, [rbp+var_20]
0x18004119b  call    SdbpOpenCompressedDatabase
0x1800411a0  test    eax, eax
0x1800411a2  jnz     short loc_1800411C5
0x1800411a4  lea     r9, aSdbpopencompre; "SdbpOpenCompressedDatabase failed to op"...
0x1800411ab  mov     r8d, 0A43h
0x1800411b1  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x1800411b8  mov     ecx, edi
0x1800411ba  call    AslLogCallPrintf
0x1800411bf  mov     rbx, [rbp+var_20]
0x1800411c3  jmp     short loc_1800411FE
0x1800411c5  mov     rbx, [rbp+var_20]
0x1800411c9  jmp     short loc_1800411DE
0x1800411cb  mov     r8d, r12d
0x1800411ce  lea     rdx, [rbp+var_18]
0x1800411d2  mov     rcx, rbx
0x1800411d5  call    SdbpValidateAndApplyCompatFlags
0x1800411da  test    eax, eax
0x1800411dc  jz      short loc_1800411FE
0x1800411de  mov     rax, rbx
0x1800411e1  jmp     short loc_180041222
0x1800411e3  lea     r9, aFailedToOpenSd; "Failed to open SDB - File size too larg"...
0x1800411ea  mov     r8d, 0A1Dh
0x1800411f0  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x1800411f7  mov     ecx, edi
0x1800411f9  call    AslLogCallPrintf
0x1800411fe  test    rbx, rbx
0x180041201  jz      short loc_180041220
0x180041203  mov     rcx, [rbx]
0x180041206  call    AslFileMappingDelete
0x18004120b  mov     rcx, gs:60h
0x180041214  mov     rdx, rbx
0x180041217  mov     rcx, [rcx+30h]
0x18004121b  call    AslFree
0x180041220  xor     eax, eax
0x180041222  mov     rcx, [rbp+var_8]
0x180041226  xor     rcx, rsp; StackCookie
0x180041229  call    __security_check_cookie
0x18004122e  lea     r11, [rsp+60h+var_s0]
0x180041233  mov     rbx, [r11+38h]
0x180041237  mov     rsi, [r11+48h]
0x18004123b  mov     rsp, r11
0x18004123e  pop     r14
0x180041240  pop     r13
0x180041242  pop     r12
0x180041244  pop     rdi
0x180041245  pop     rbp
0x180041246  retn
```
