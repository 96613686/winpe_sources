# ClusterResourceTypeEnumHelper(_HRESTYPEENUM *,ulong,ulong *,ushort * *)

- ea: `0x18007975c`
- end: `0x180079902`
- name: `?ClusterResourceTypeEnumHelper@@YAJPEAU_HRESTYPEENUM@@KPEAKPEAPEAG@Z`
- size: `422`
- prototype: `__int64 __fastcall(HRESTYPEENUM hResTypeEnum, DWORD dwIndex, LPDWORD lpdwType, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013694`
- `0x180071a34`

## callees

- `0x180006764`
- `0x18001156c`
- `0x18007975c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007983e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007984c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800798e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007983e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007984c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800798e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180079794`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007985f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180079794`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007985f`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x180079835`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x180079835`
- `CLUSAPI!ClusterResourceTypeEnum` at `0x1800797c1`
- `CLUSAPI!ClusterResourceTypeEnum` at `0x180079886`
- `CLUSAPI!ClusterResourceTypeEnum` at `0x1800797c1`
- `CLUSAPI!ClusterResourceTypeEnum` at `0x180079886`

## string_xrefs

- `0x180079818`: `com\complus\dtc\shared\util\clusterhelper.cpp`

## pseudocode

```c
__int64 __fastcall ClusterResourceTypeEnumHelper(
        HRESTYPEENUM hResTypeEnum,
        DWORD dwIndex,
        LPDWORD lpdwType,
        unsigned __int16 **a4)
{
  WCHAR *v8; // rdi
  unsigned int v9; // ebx
  signed int v10; // eax
  int StringW; // eax
  unsigned __int16 *v12; // rsi
  unsigned int v13; // r9d
  SIZE_T v14; // rcx
  signed int v15; // eax
  int v16; // eax
  LPDWORD lpcchName; // [rsp+20h] [rbp-20h]
  LPDWORD lpcchNamea; // [rsp+20h] [rbp-20h]
  LPVOID pv[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD cchName; // [rsp+88h] [rbp+48h] BYREF

  cchName = 128;
  *a4 = 0;
  v8 = (WCHAR *)CoTaskMemAlloc(0x100u);
  if ( !v8 )
    goto LABEL_2;
  v10 = ClusterResourceTypeEnum(hResTypeEnum, dwIndex, lpdwType, v8, &cchName);
  v9 = v10;
  if ( !v10 )
    goto LABEL_17;
  if ( v10 != 234 )
  {
    if ( v10 > 0 )
      v9 = (unsigned __int16)v10 | 0x80070000;
    LODWORD(lpcchName) = cchName;
    pv[0] = 0;
    StringW = MakeStringW(
                (unsigned __int16 **)pv,
                L"hResTypeEnum: %x dwEnumIndex:%d lpcchName: %d",
                hResTypeEnum,
                dwIndex,
                lpcchName);
    v12 = (unsigned __int16 *)pv[0];
    if ( StringW < 0 )
      goto LABEL_10;
    v13 = 118;
LABEL_9:
    TraceFileW(v9, v12, L"com\\complus\\dtc\\shared\\util\\clusterhelper.cpp", v13);
LABEL_10:
    FailedClusterAPIToEventLog(L"ClusterResourceTypeEnum", v9, v12);
    CoTaskMemFree(v12);
    goto LABEL_18;
  }
  CoTaskMemFree(v8);
  v14 = 2LL * ++cchName;
  v8 = (WCHAR *)CoTaskMemAlloc(v14);
  if ( v8 )
  {
    v15 = ClusterResourceTypeEnum(hResTypeEnum, dwIndex, lpdwType, v8, &cchName);
    v9 = v15;
    if ( v15 )
    {
      if ( v15 > 0 )
        v9 = (unsigned __int16)v15 | 0x80070000;
      LODWORD(lpcchNamea) = cchName;
      pv[0] = 0;
      v16 = MakeStringW(
              (unsigned __int16 **)pv,
              L"hResTypeEnum: %x dwEnumIndex:%d lpcchName: %d",
              hResTypeEnum,
              dwIndex,
              lpcchNamea);
      v12 = (unsigned __int16 *)pv[0];
      if ( v16 < 0 )
        goto LABEL_10;
      v13 = 156;
      goto LABEL_9;
    }
LABEL_17:
    v9 = 0;
    *a4 = v8;
    v8 = 0;
    goto LABEL_18;
  }
LABEL_2:
  v9 = -2147024882;
LABEL_18:
  CoTaskMemFree(v8);
  return v9;
}

```

## disassembly

```asm
0x18007975c  mov     [rsp-28h+arg_0], rbx
0x180079761  mov     [rsp-28h+arg_8], rsi
0x180079766  push    rbp
0x180079767  push    rdi
0x180079768  push    r12
0x18007976a  push    r14
0x18007976c  push    r15
0x18007976e  mov     rbp, rsp
0x180079771  sub     rsp, 40h
0x180079775  mov     r15, rcx
0x180079778  mov     [rbp+cchName], 80h
0x18007977f  mov     ecx, 100h; cb
0x180079784  mov     qword ptr [r9], 0
0x18007978b  mov     rsi, r9
0x18007978e  mov     r12, r8
0x180079791  mov     r14d, edx
0x180079794  call    cs:__imp_CoTaskMemAlloc
0x18007979a  mov     rdi, rax
0x18007979d  test    rax, rax
0x1800797a0  jnz     short loc_1800797AC
0x1800797a2  mov     ebx, 8007000Eh
0x1800797a7  jmp     loc_1800798E0
0x1800797ac  lea     rax, [rbp+cchName]
0x1800797b0  mov     r9, rdi; lpszName
0x1800797b3  mov     r8, r12; lpdwType
0x1800797b6  mov     [rsp+40h+lpcchName], rax; lpcchName
0x1800797bb  mov     edx, r14d; dwIndex
0x1800797be  mov     rcx, r15; hResTypeEnum
0x1800797c1  call    cs:__imp_ClusterResourceTypeEnum
0x1800797c7  mov     ebx, eax
0x1800797c9  test    eax, eax
0x1800797cb  jz      loc_1800798D9
0x1800797d1  cmp     eax, 0EAh
0x1800797d6  jz      short loc_180079849
0x1800797d8  test    eax, eax
0x1800797da  jle     short loc_1800797E5
0x1800797dc  movzx   ebx, ax
0x1800797df  or      ebx, 80070000h
0x1800797e5  mov     eax, [rbp+cchName]
0x1800797e8  lea     rdx, aHrestypeenumXD; "hResTypeEnum: %x dwEnumIndex:%d lpcchNa"...
0x1800797ef  mov     r9d, r14d
0x1800797f2  mov     dword ptr [rsp+40h+lpcchName], eax
0x1800797f6  mov     r8, r15
0x1800797f9  mov     [rbp+pv], 0
0x180079801  lea     rcx, [rbp+pv]; unsigned __int16 **
0x180079805  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x18007980a  mov     rsi, [rbp+pv]
0x18007980e  test    eax, eax
0x180079810  js      short loc_180079829
0x180079812  mov     r9d, 76h ; 'v'; unsigned int
0x180079818  lea     r8, aComComplusDtcS_17; "com\\complus\\dtc\\shared\\util\\cluste"...
0x18007981f  mov     rdx, rsi; unsigned __int16 *
0x180079822  mov     ecx, ebx; int
0x180079824  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x180079829  mov     r8, rsi
0x18007982c  lea     rcx, aClusterresourc; "ClusterResourceTypeEnum"
0x180079833  mov     edx, ebx
0x180079835  call    cs:__imp_FailedClusterAPIToEventLog
0x18007983b  mov     rcx, rsi; pv
0x18007983e  call    cs:__imp_CoTaskMemFree
0x180079844  jmp     loc_1800798E0
0x180079849  mov     rcx, rdi; pv
0x18007984c  call    cs:__imp_CoTaskMemFree
0x180079852  mov     eax, [rbp+cchName]
0x180079855  inc     eax
0x180079857  mov     ecx, eax
0x180079859  add     rcx, rcx; cb
0x18007985c  mov     [rbp+cchName], eax
0x18007985f  call    cs:__imp_CoTaskMemAlloc
0x180079865  mov     rdi, rax
0x180079868  test    rax, rax
0x18007986b  jz      loc_1800797A2
0x180079871  lea     rax, [rbp+cchName]
0x180079875  mov     r9, rdi; lpszName
0x180079878  mov     r8, r12; lpdwType
0x18007987b  mov     [rsp+40h+lpcchName], rax; lpcchName
0x180079880  mov     edx, r14d; dwIndex
0x180079883  mov     rcx, r15; hResTypeEnum
0x180079886  call    cs:__imp_ClusterResourceTypeEnum
0x18007988c  mov     ebx, eax
0x18007988e  test    eax, eax
0x180079890  jz      short loc_1800798D9
0x180079892  jle     short loc_18007989D
0x180079894  movzx   ebx, ax
0x180079897  or      ebx, 80070000h
0x18007989d  mov     eax, [rbp+cchName]
0x1800798a0  lea     rdx, aHrestypeenumXD; "hResTypeEnum: %x dwEnumIndex:%d lpcchNa"...
0x1800798a7  mov     r9d, r14d
0x1800798aa  mov     dword ptr [rsp+40h+lpcchName], eax
0x1800798ae  mov     r8, r15
0x1800798b1  mov     [rbp+pv], 0
0x1800798b9  lea     rcx, [rbp+pv]; unsigned __int16 **
0x1800798bd  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x1800798c2  mov     rsi, [rbp+pv]
0x1800798c6  test    eax, eax
0x1800798c8  js      loc_180079829
0x1800798ce  mov     r9d, 9Ch
0x1800798d4  jmp     loc_180079818
0x1800798d9  xor     ebx, ebx
0x1800798db  mov     [rsi], rdi
0x1800798de  xor     edi, edi
0x1800798e0  mov     rcx, rdi; pv
0x1800798e3  call    cs:__imp_CoTaskMemFree
0x1800798e9  mov     rsi, [rsp+40h+arg_8]
0x1800798ee  mov     eax, ebx
0x1800798f0  mov     rbx, [rsp+40h+arg_0]
0x1800798f5  add     rsp, 40h
0x1800798f9  pop     r15
0x1800798fb  pop     r14
0x1800798fd  pop     r12
0x1800798ff  pop     rdi
0x180079900  pop     rbp
0x180079901  retn
```
