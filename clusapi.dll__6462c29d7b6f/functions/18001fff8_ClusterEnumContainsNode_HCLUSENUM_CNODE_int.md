# ClusterEnumContainsNode(_HCLUSENUM *,_CNODE *,int *)

- ea: `0x18001fff8`
- end: `0x180020187`
- name: `?ClusterEnumContainsNode@@YAKPEAU_HCLUSENUM@@PEAU_CNODE@@PEAH@Z`
- size: `399`
- prototype: `unsigned int __fastcall(HCLUSENUM hEnum, struct _CNODE *, int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001ff2c`
- `0x180058330`

## callees

- `0x180003c14`
- `0x180014578`
- `0x18001fff8`
- `0x180026ef4`
- `0x18002acc0`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180020145`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180020145`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002015a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002015a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800200b6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800200b6`

## pseudocode

```c
__int64 __fastcall ClusterEnumContainsNode(HCLUSENUM hEnum, struct _CNODE *a2, int *a3)
{
  __int64 result; // rax
  const wchar_t *v7; // rcx
  int v8; // ebx
  int v9; // ebx
  SIZE_T v10; // r15
  HLOCAL v11; // rdi
  DWORD i; // esi
  DWORD v13; // eax
  DWORD dwType[14]; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int64 cchName; // [rsp+88h] [rbp+20h] BYREF

  if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSENUM *>(
                           hEnum,
                           hEnum) )
    return 6;
  v7 = (const wchar_t *)*((_QWORD *)a2 + 5);
  cchName = 0;
  *a3 = 0;
  v8 = StringCchLengthW(v7, 0x7FFFFFFFu, &cchName);
  if ( v8 < 0 )
  {
    TraceMsg(2u, 0, (__int64)L"ClusterEnumContainsNode", 6420, L"Cannot determine length of node name.");
    if ( (v8 & 0x1FFF0000) != 0x70000 )
      return (unsigned int)v8;
    result = (unsigned __int16)v8;
    if ( !(_WORD)v8 )
      return (unsigned int)v8;
    return result;
  }
  v9 = cchName + 2;
  v10 = 2 * (cchName + 2);
  v11 = LocalAlloc(0, v10);
  if ( !v11 )
  {
    TraceMsg(2u, 0, (__int64)L"ClusterEnumContainsNode", 6428, L"Cannot allocate memory.");
    return 8;
  }
  for ( i = 0; ; ++i )
  {
    memset_0(v11, 0, v10);
    LODWORD(cchName) = v9;
    v13 = ClusterEnum(hEnum, i, dwType, (LPWSTR)v11, (LPDWORD)&cchName);
    if ( !v13 )
      break;
    if ( v13 == 259 )
      goto LABEL_13;
LABEL_16:
    ;
  }
  if ( CompareStringW(0x7Fu, 1u, *((PCNZWCH *)a2 + 5), v9 - 2, (PCNZWCH)v11, cchName) != 2 )
    goto LABEL_16;
  *a3 = 1;
LABEL_13:
  LocalFree(v11);
  return 0;
}

```

## disassembly

```asm
0x18001fff8  mov     [rsp+arg_0], rbx
0x18001fffd  mov     [rsp+arg_8], rbp
0x180020002  push    rsi
0x180020003  push    rdi
0x180020004  push    r12
0x180020006  push    r14
0x180020008  push    r15
0x18002000a  sub     rsp, 40h
0x18002000e  mov     rbp, rdx
0x180020011  mov     r14, r8
0x180020014  mov     rdx, rcx
0x180020017  mov     r12, rcx
0x18002001a  call    ??$Contains@PEAU_HCLUSENUM@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSENUM@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSENUM *>(_HCLUSENUM *)
0x18002001f  test    al, al
0x180020021  jnz     short loc_18002002D
0x180020023  mov     eax, 6
0x180020028  jmp     loc_180020162
0x18002002d  mov     rcx, [rbp+28h]; wchar_t *
0x180020031  lea     r8, [rsp+68h+cchName]; unsigned __int64 *
0x180020039  mov     edx, 7FFFFFFFh; unsigned __int64
0x18002003e  mov     [rsp+68h+cchName], 0
0x18002004a  mov     dword ptr [r14], 0
0x180020051  call    ?StringCchLengthW@@YAJPEB_W_KPEA_K@Z; StringCchLengthW(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x180020056  mov     ebx, eax
0x180020058  test    eax, eax
0x18002005a  jns     short loc_1800200A1
0x18002005c  xor     edx, edx
0x18002005e  lea     rax, aCannotDetermin_0; "Cannot determine length of node name."
0x180020065  mov     r9d, 1914h
0x18002006b  mov     [rsp+68h+lpcchName], rax
0x180020070  lea     r8, aClusterenumcon; "ClusterEnumContainsNode"
0x180020077  lea     ecx, [rdx+2]
0x18002007a  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18002007f  mov     ecx, ebx
0x180020081  and     ecx, 1FFF0000h
0x180020087  cmp     ecx, 70000h
0x18002008d  jnz     short loc_18002009A
0x18002008f  movzx   eax, bx
0x180020092  test    eax, eax
0x180020094  jnz     loc_180020162
0x18002009a  mov     eax, ebx
0x18002009c  jmp     loc_180020162
0x1800200a1  mov     rbx, [rsp+68h+cchName]
0x1800200a9  xor     ecx, ecx; uFlags
0x1800200ab  add     rbx, 2
0x1800200af  lea     r15, [rbx+rbx]
0x1800200b3  mov     rdx, r15; uBytes
0x1800200b6  call    cs:__imp_LocalAlloc
0x1800200bc  mov     rdi, rax
0x1800200bf  test    rax, rax
0x1800200c2  jnz     short loc_1800200EC
0x1800200c4  lea     rax, aCannotAllocate; "Cannot allocate memory."
0x1800200cb  mov     r9d, 191Ch
0x1800200d1  lea     r8, aClusterenumcon; "ClusterEnumContainsNode"
0x1800200d8  mov     [rsp+68h+lpcchName], rax
0x1800200dd  xor     edx, edx
0x1800200df  lea     ecx, [rdi+2]
0x1800200e2  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800200e7  lea     eax, [rdi+8]
0x1800200ea  jmp     short loc_180020162
0x1800200ec  xor     esi, esi
0x1800200ee  mov     r8, r15; Size
0x1800200f1  xor     edx, edx; Val
0x1800200f3  mov     rcx, rdi; void *
0x1800200f6  call    memset_0
0x1800200fb  lea     rax, [rsp+68h+cchName]
0x180020103  mov     dword ptr [rsp+68h+cchName], ebx
0x18002010a  mov     r9, rdi; lpszName
0x18002010d  mov     [rsp+68h+lpcchName], rax; lpcchName
0x180020112  lea     r8, [rsp+68h+dwType]; lpdwType
0x180020117  mov     edx, esi; dwIndex
0x180020119  mov     rcx, r12; hEnum
0x18002011c  call    ClusterEnum
0x180020121  test    eax, eax
0x180020123  jnz     short loc_180020179
0x180020125  mov     eax, dword ptr [rsp+68h+cchName]
0x18002012c  lea     r9d, [rbx-2]; cchCount1
0x180020130  mov     r8, [rbp+28h]; lpString1
0x180020134  mov     edx, 1; dwCmpFlags
0x180020139  mov     [rsp+68h+cchCount2], eax; cchCount2
0x18002013d  mov     [rsp+68h+lpcchName], rdi; lpString2
0x180020142  lea     ecx, [rdx+7Eh]; Locale
0x180020145  call    cs:__imp_CompareStringW
0x18002014b  cmp     eax, 2
0x18002014e  jnz     short loc_180020180
0x180020150  mov     dword ptr [r14], 1
0x180020157  mov     rcx, rdi; hMem
0x18002015a  call    cs:__imp_LocalFree
0x180020160  xor     eax, eax
0x180020162  mov     rbx, [rsp+68h+arg_0]
0x180020167  mov     rbp, [rsp+68h+arg_8]
0x18002016c  add     rsp, 40h
0x180020170  pop     r15
0x180020172  pop     r14
0x180020174  pop     r12
0x180020176  pop     rdi
0x180020177  pop     rsi
0x180020178  retn
0x180020179  cmp     eax, 103h
0x18002017e  jz      short loc_180020157
0x180020180  inc     esi
0x180020182  jmp     loc_1800200EE
```
