# CreateCertificateName(bool,HKEY__ *,uchar const *,ulong,char *,ulong *)

- ea: `0x180031628`
- end: `0x18003195d`
- name: `?CreateCertificateName@@YAJ_NPEAUHKEY__@@PEBEKPEADPEAK@Z`
- size: `821`
- prototype: `int(bool, HKEY, const unsigned __int8 *, unsigned int, char *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180034b80`
- `0x180037648`

## callees

- `0x1800315b0`
- `0x180031628`
- `0x1800392b0`
- `0x18003935c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031762`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031762`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800316ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003173b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031793`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031814`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031878`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800318a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031915`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003193f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800316ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003173b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031793`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031814`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031878`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800318a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031915`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003193f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031698`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031727`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003174e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003177f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031800`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031864`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003188e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031901`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003192b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031698`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031727`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003174e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003177f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031800`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031864`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003188e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031901`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003192b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031703`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800317e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031703`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800317e5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800316f1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800317d3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800316f1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800317d3`
- `DMCmnUtils!OmDmRegistryAllocAndGetString` at `0x18003167d`
- `DMCmnUtils!OmDmRegistryAllocAndGetString` at `0x18003167d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CreateCertificateName(
        unsigned __int8 a1,
        HKEY a2,
        const char *a3,
        unsigned int a4,
        char *a5,
        unsigned int *a6)
{
  int v8; // r14d
  unsigned int v9; // r15d
  __int64 v10; // rax
  int String; // edi
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v15; // eax
  SIZE_T cbMultiByte; // rsi
  signed int LastError; // eax
  unsigned int v18; // ebx
  void *v19; // rdi
  HANDLE v20; // rax
  HANDLE v21; // rax
  CHAR *lpMultiByteStr; // rax
  CHAR *v23; // rdi
  void *v24; // rbx
  HANDLE v25; // rax
  int v26; // edx
  signed int v27; // eax
  HANDLE v28; // rax
  unsigned int v29; // edx
  unsigned int v30; // ecx
  int v31; // r14d
  HANDLE v32; // rax
  void *v33; // rbx
  HANDLE v34; // rax
  unsigned int v35; // esi
  HANDLE v36; // rax
  void *v37; // rbx
  HANDLE v38; // rax
  LPVOID lpMem[2]; // [rsp+40h] [rbp-10h] BYREF

  v8 = a1;
  lpMem[0] = 0;
  lpMem[1] = 0;
  v9 = 61;
  if ( a4 <= 0x3D )
    v9 = a4;
  v10 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator&(lpMem);
  String = OmDmRegistryAllocAndGetString(a2, L"EnrollmentID", 1, v10);
  if ( String < 0 )
  {
    v12 = lpMem[0];
    if ( lpMem[0] )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v12);
    }
    return (unsigned int)String;
  }
  v15 = WideCharToMultiByte(0, 0x400u, (LPCWCH)lpMem[0], -1, 0, 0, 0, 0);
  cbMultiByte = v15;
  if ( !v15 )
  {
    LastError = GetLastError();
    v18 = LastError;
    if ( LastError > 0 )
      v18 = (unsigned __int16)LastError | 0x80070000;
LABEL_10:
    v19 = lpMem[0];
    if ( lpMem[0] )
    {
      v20 = GetProcessHeap();
      HeapFree(v20, 0, v19);
    }
    return v18;
  }
  v21 = GetProcessHeap();
  lpMultiByteStr = (CHAR *)HeapAlloc(v21, 0, cbMultiByte);
  v23 = lpMultiByteStr;
  if ( lpMultiByteStr )
  {
    v26 = WideCharToMultiByte(0, 0x400u, (LPCWCH)lpMem[0], -1, lpMultiByteStr, cbMultiByte, 0, 0);
    if ( !v26 )
    {
      v27 = GetLastError();
      v18 = v27;
      if ( v27 > 0 )
        v18 = (unsigned __int16)v27 | 0x80070000;
      v28 = GetProcessHeap();
      HeapFree(v28, 0, v23);
      goto LABEL_10;
    }
    v29 = 4 * v8 + v9 + 2 + v26;
    v30 = 4 * v8 + 65;
    if ( v29 <= v30 )
      v30 = v29;
    *a6 = v30;
    if ( (_BYTE)v8 && (v31 = StringCbCatA(a5, v30, qword_1800657E8), v31 < 0)
      || (v31 = StringCbCatNA(a5, *a6, v23, 63 - v9), v31 < 0)
      || (v31 = StringCbCatA(a5, *a6, "!"), v31 < 0) )
    {
      v32 = GetProcessHeap();
      HeapFree(v32, 0, v23);
      v33 = lpMem[0];
      if ( lpMem[0] )
      {
        v34 = GetProcessHeap();
        HeapFree(v34, 0, v33);
      }
      return (unsigned int)v31;
    }
    else
    {
      v35 = StringCbCatNA(a5, *a6, a3, v9);
      v36 = GetProcessHeap();
      HeapFree(v36, 0, v23);
      v37 = lpMem[0];
      if ( lpMem[0] )
      {
        v38 = GetProcessHeap();
        HeapFree(v38, 0, v37);
      }
      return v35;
    }
  }
  else
  {
    v24 = lpMem[0];
    if ( lpMem[0] )
    {
      v25 = GetProcessHeap();
      HeapFree(v25, 0, v24);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180031628  push    rbp
0x18003162a  push    rbx
0x18003162b  push    rsi
0x18003162c  push    rdi
0x18003162d  push    r12
0x18003162f  push    r14
0x180031631  push    r15
0x180031633  mov     rbp, rsp
0x180031636  sub     rsp, 50h
0x18003163a  mov     r12, r8
0x18003163d  mov     rbx, rdx
0x180031640  movzx   r14d, cl
0x180031644  mov     [rbp+lpMem], 0
0x18003164c  mov     [rbp+var_8], 0
0x180031654  mov     r15d, 3Dh ; '='
0x18003165a  cmp     r9d, r15d
0x18003165d  cmovbe  r15d, r9d
0x180031661  lea     rcx, [rbp+lpMem]
0x180031665  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AHPEAX@Z$1?SafeHeapFree@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,int (*)(void *),&SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator&(void)
0x18003166a  mov     r9, rax
0x18003166d  mov     r8d, 1
0x180031673  lea     rdx, aEnrollmentid; "EnrollmentID"
0x18003167a  mov     rcx, rbx
0x18003167d  call    cs:__imp_?OmDmRegistryAllocAndGetString@@YAJPEAUHKEY__@@PEBGW4AllocFunction@@PEAPEAG@Z; OmDmRegistryAllocAndGetString(HKEY__ *,ushort const *,AllocFunction,ushort * *)
0x180031684  nop     dword ptr [rax+rax+00h]
0x180031689  mov     edi, eax
0x18003168b  test    eax, eax
0x18003168d  jns     short loc_1800316BF
0x18003168f  mov     rbx, [rbp+lpMem]
0x180031693  test    rbx, rbx
0x180031696  jz      short loc_1800316B8
0x180031698  call    cs:__imp_GetProcessHeap
0x18003169f  nop     dword ptr [rax+rax+00h]
0x1800316a4  mov     rcx, rax; hHeap
0x1800316a7  mov     r8, rbx; lpMem
0x1800316aa  xor     edx, edx; dwFlags
0x1800316ac  call    cs:__imp_HeapFree
0x1800316b3  nop     dword ptr [rax+rax+00h]
0x1800316b8  mov     eax, edi
0x1800316ba  jmp     loc_18003194D
0x1800316bf  mov     [rsp+50h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800316c8  mov     [rsp+50h+lpDefaultChar], 0; lpDefaultChar
0x1800316d1  mov     [rsp+50h+cbMultiByte], 0; cbMultiByte
0x1800316d9  mov     [rsp+50h+lpMultiByteStr], 0; lpMultiByteStr
0x1800316e2  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800316e6  mov     r8, [rbp+lpMem]; lpWideCharStr
0x1800316ea  mov     edx, 400h; dwFlags
0x1800316ef  xor     ecx, ecx; CodePage
0x1800316f1  call    cs:__imp_WideCharToMultiByte
0x1800316f8  nop     dword ptr [rax+rax+00h]
0x1800316fd  mov     esi, eax
0x1800316ff  test    eax, eax
0x180031701  jnz     short loc_18003174E
0x180031703  call    cs:__imp_GetLastError
0x18003170a  nop     dword ptr [rax+rax+00h]
0x18003170f  mov     ebx, eax
0x180031711  test    eax, eax
0x180031713  jle     short loc_18003171E
0x180031715  movzx   ebx, ax
0x180031718  or      ebx, 80070000h
0x18003171e  mov     rdi, [rbp+lpMem]
0x180031722  test    rdi, rdi
0x180031725  jz      short loc_180031747
0x180031727  call    cs:__imp_GetProcessHeap
0x18003172e  nop     dword ptr [rax+rax+00h]
0x180031733  mov     rcx, rax; hHeap
0x180031736  mov     r8, rdi; lpMem
0x180031739  xor     edx, edx; dwFlags
0x18003173b  call    cs:__imp_HeapFree
0x180031742  nop     dword ptr [rax+rax+00h]
0x180031747  mov     eax, ebx
0x180031749  jmp     loc_18003194D
0x18003174e  call    cs:__imp_GetProcessHeap
0x180031755  nop     dword ptr [rax+rax+00h]
0x18003175a  mov     rcx, rax; hHeap
0x18003175d  mov     r8, rsi; dwBytes
0x180031760  xor     edx, edx; dwFlags
0x180031762  call    cs:__imp_HeapAlloc
0x180031769  nop     dword ptr [rax+rax+00h]
0x18003176e  mov     rdi, rax
0x180031771  test    rax, rax
0x180031774  jnz     short loc_1800317A9
0x180031776  mov     rbx, [rbp+lpMem]
0x18003177a  test    rbx, rbx
0x18003177d  jz      short loc_18003179F
0x18003177f  call    cs:__imp_GetProcessHeap
0x180031786  nop     dword ptr [rax+rax+00h]
0x18003178b  mov     rcx, rax; hHeap
0x18003178e  mov     r8, rbx; lpMem
0x180031791  xor     edx, edx; dwFlags
0x180031793  call    cs:__imp_HeapFree
0x18003179a  nop     dword ptr [rax+rax+00h]
0x18003179f  mov     eax, 8007000Eh
0x1800317a4  jmp     loc_18003194D
0x1800317a9  mov     [rsp+50h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800317b2  mov     [rsp+50h+lpDefaultChar], 0; lpDefaultChar
0x1800317bb  mov     [rsp+50h+cbMultiByte], esi; cbMultiByte
0x1800317bf  mov     [rsp+50h+lpMultiByteStr], rdi; lpMultiByteStr
0x1800317c4  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800317c8  mov     r8, [rbp+lpMem]; lpWideCharStr
0x1800317cc  mov     edx, 400h; dwFlags
0x1800317d1  xor     ecx, ecx; CodePage
0x1800317d3  call    cs:__imp_WideCharToMultiByte
0x1800317da  nop     dword ptr [rax+rax+00h]
0x1800317df  mov     edx, eax
0x1800317e1  test    eax, eax
0x1800317e3  jnz     short loc_180031825
0x1800317e5  call    cs:__imp_GetLastError
0x1800317ec  nop     dword ptr [rax+rax+00h]
0x1800317f1  mov     ebx, eax
0x1800317f3  test    eax, eax
0x1800317f5  jle     short loc_180031800
0x1800317f7  movzx   ebx, ax
0x1800317fa  or      ebx, 80070000h
0x180031800  call    cs:__imp_GetProcessHeap
0x180031807  nop     dword ptr [rax+rax+00h]
0x18003180c  mov     rcx, rax; hHeap
0x18003180f  mov     r8, rdi; lpMem
0x180031812  xor     edx, edx; dwFlags
0x180031814  call    cs:__imp_HeapFree
0x18003181b  nop     dword ptr [rax+rax+00h]
0x180031820  jmp     loc_18003171E
0x180031825  lea     ecx, ds:0[r14*4]
0x18003182d  lea     eax, [r15+2]
0x180031831  add     eax, ecx
0x180031833  add     edx, eax
0x180031835  add     ecx, 41h ; 'A'
0x180031838  cmp     edx, ecx
0x18003183a  cmovbe  ecx, edx
0x18003183d  mov     rsi, [rbp+arg_28]
0x180031841  mov     [rsi], ecx
0x180031843  mov     rbx, [rbp+arg_20]
0x180031847  test    r14b, r14b
0x18003184a  jz      short loc_1800318B6
0x18003184c  mov     edx, ecx; unsigned __int64
0x18003184e  lea     r8, qword_1800657E8; char *
0x180031855  mov     rcx, rbx; char *
0x180031858  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x18003185d  mov     r14d, eax
0x180031860  test    eax, eax
0x180031862  jns     short loc_1800318B6
0x180031864  call    cs:__imp_GetProcessHeap
0x18003186b  nop     dword ptr [rax+rax+00h]
0x180031870  mov     rcx, rax; hHeap
0x180031873  mov     r8, rdi; lpMem
0x180031876  xor     edx, edx; dwFlags
0x180031878  call    cs:__imp_HeapFree
0x18003187f  nop     dword ptr [rax+rax+00h]
0x180031884  nop
0x180031885  mov     rbx, [rbp+lpMem]
0x180031889  test    rbx, rbx
0x18003188c  jz      short loc_1800318AE
0x18003188e  call    cs:__imp_GetProcessHeap
0x180031895  nop     dword ptr [rax+rax+00h]
0x18003189a  mov     rcx, rax; hHeap
0x18003189d  mov     r8, rbx; lpMem
0x1800318a0  xor     edx, edx; dwFlags
0x1800318a2  call    cs:__imp_HeapFree
0x1800318a9  nop     dword ptr [rax+rax+00h]
0x1800318ae  mov     eax, r14d
0x1800318b1  jmp     loc_18003194D
0x1800318b6  mov     r9d, 3Fh ; '?'
0x1800318bc  sub     r9d, r15d; unsigned __int64
0x1800318bf  mov     edx, [rsi]; unsigned __int64
0x1800318c1  mov     r8, rdi; char *
0x1800318c4  mov     rcx, rbx; char *
0x1800318c7  call    ?StringCbCatNA@@YAJPEAD_KPEBD1@Z; StringCbCatNA(char *,unsigned __int64,char const *,unsigned __int64)
0x1800318cc  mov     r14d, eax
0x1800318cf  test    eax, eax
0x1800318d1  js      short loc_180031864
0x1800318d3  mov     edx, [rsi]; unsigned __int64
0x1800318d5  lea     r8, asc_180063734; "!"
0x1800318dc  mov     rcx, rbx; char *
0x1800318df  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x1800318e4  mov     r14d, eax
0x1800318e7  test    eax, eax
0x1800318e9  js      loc_180031864
0x1800318ef  mov     r9d, r15d; unsigned __int64
0x1800318f2  mov     edx, [rsi]; unsigned __int64
0x1800318f4  mov     r8, r12; char *
0x1800318f7  mov     rcx, rbx; char *
0x1800318fa  call    ?StringCbCatNA@@YAJPEAD_KPEBD1@Z; StringCbCatNA(char *,unsigned __int64,char const *,unsigned __int64)
0x1800318ff  mov     esi, eax
0x180031901  call    cs:__imp_GetProcessHeap
0x180031908  nop     dword ptr [rax+rax+00h]
0x18003190d  mov     rcx, rax; hHeap
0x180031910  mov     r8, rdi; lpMem
0x180031913  xor     edx, edx; dwFlags
0x180031915  call    cs:__imp_HeapFree
0x18003191c  nop     dword ptr [rax+rax+00h]
0x180031921  nop
0x180031922  mov     rbx, [rbp+lpMem]
0x180031926  test    rbx, rbx
0x180031929  jz      short loc_18003194B
0x18003192b  call    cs:__imp_GetProcessHeap
0x180031932  nop     dword ptr [rax+rax+00h]
0x180031937  mov     rcx, rax; hHeap
0x18003193a  mov     r8, rbx; lpMem
0x18003193d  xor     edx, edx; dwFlags
0x18003193f  call    cs:__imp_HeapFree
0x180031946  nop     dword ptr [rax+rax+00h]
0x18003194b  mov     eax, esi
0x18003194d  add     rsp, 50h
0x180031951  pop     r15
0x180031953  pop     r14
0x180031955  pop     r12
0x180031957  pop     rdi
0x180031958  pop     rsi
0x180031959  pop     rbx
0x18003195a  pop     rbp
0x18003195b  retn
```
