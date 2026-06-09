# IsLocalSystemCluster(void)

- ea: `0x18000b810`
- end: `0x18000b956`
- name: `?IsLocalSystemCluster@@YA_NXZ`
- size: `326`
- prototype: `bool(void)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000b76c`
- `0x18000b810`
- `0x18000c39c`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000b860`
- `KERNEL32!GetProcAddress` at `0x18000b860`
- `KERNEL32!LoadLibraryW` at `0x18000b81b`
- `KERNEL32!LoadLibraryW` at `0x18000b81b`

## string_xrefs

- `0x18000b814`: `clusapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char IsLocalSystemCluster(void)
{
  HMODULE LibraryW; // rax
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  FARPROC ProcAddress; // rax
  unsigned int v5; // [rsp+30h] [rbp+8h] BYREF
  HMODULE v6; // [rsp+38h] [rbp+10h] BYREF

  LibraryW = LoadLibraryW(L"clusapi.dll");
  v6 = LibraryW;
  if ( !LibraryW )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_22;
    v2 = 20;
LABEL_21:
    WPP_SF_(v1[2], v2, &WPP_f8138a78677f34b3e5f704385132758d_Traceguids);
LABEL_22:
    CAutoFreeLibrary::~CAutoFreeLibrary((CAutoFreeLibrary *)&v6);
    return 0;
  }
  ProcAddress = GetProcAddress(LibraryW, "GetNodeClusterState");
  if ( !ProcAddress )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_22;
    v2 = 21;
    goto LABEL_21;
  }
  v5 = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, unsigned int *))ProcAddress)(0, &v5) )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_22;
    v2 = 22;
    goto LABEL_21;
  }
  if ( v5 < 2 )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_22;
    v2 = 23;
    goto LABEL_21;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_f8138a78677f34b3e5f704385132758d_Traceguids);
  CAutoFreeLibrary::~CAutoFreeLibrary((CAutoFreeLibrary *)&v6);
  return 1;
}

```

## disassembly

```asm
0x18000b810  sub     rsp, 28h
0x18000b814  lea     rcx, LibFileName; "clusapi.dll"
0x18000b81b  call    cs:__imp_LoadLibraryW
0x18000b821  mov     [rsp+28h+arg_8], rax
0x18000b826  test    rax, rax
0x18000b829  jnz     short loc_18000B856
0x18000b82b  lea     rax, WPP_GLOBAL_Control
0x18000b832  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b839  cmp     rcx, rax
0x18000b83c  jz      loc_18000B945
0x18000b842  test    byte ptr [rcx+1Ch], 4
0x18000b846  jz      loc_18000B945
0x18000b84c  mov     edx, 14h
0x18000b851  jmp     loc_18000B934
0x18000b856  lea     rdx, aGetnodecluster; "GetNodeClusterState"
0x18000b85d  mov     rcx, rax; hModule
0x18000b860  call    cs:__imp_GetProcAddress
0x18000b866  test    rax, rax
0x18000b869  jnz     short loc_18000B896
0x18000b86b  lea     rax, WPP_GLOBAL_Control
0x18000b872  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b879  cmp     rcx, rax
0x18000b87c  jz      loc_18000B945
0x18000b882  test    byte ptr [rcx+1Ch], 4
0x18000b886  jz      loc_18000B945
0x18000b88c  mov     edx, 15h
0x18000b891  jmp     loc_18000B934
0x18000b896  mov     [rsp+28h+arg_0], 0
0x18000b89e  lea     rdx, [rsp+28h+arg_0]
0x18000b8a3  xor     ecx, ecx
0x18000b8a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8aa  test    eax, eax
0x18000b8ac  jz      short loc_18000B8D2
0x18000b8ae  lea     rax, WPP_GLOBAL_Control
0x18000b8b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8bc  cmp     rcx, rax
0x18000b8bf  jz      loc_18000B945
0x18000b8c5  test    byte ptr [rcx+1Ch], 4
0x18000b8c9  jz      short loc_18000B945
0x18000b8cb  mov     edx, 16h
0x18000b8d0  jmp     short loc_18000B934
0x18000b8d2  cmp     [rsp+28h+arg_0], 2
0x18000b8d7  jb      short loc_18000B916
0x18000b8d9  lea     rax, WPP_GLOBAL_Control
0x18000b8e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8e7  cmp     rcx, rax
0x18000b8ea  jz      short loc_18000B908
0x18000b8ec  test    byte ptr [rcx+1Ch], 4
0x18000b8f0  jz      short loc_18000B908
0x18000b8f2  mov     edx, 18h
0x18000b8f7  lea     r8, WPP_f8138a78677f34b3e5f704385132758d_Traceguids
0x18000b8fe  mov     rcx, [rcx+10h]
0x18000b902  call    WPP_SF_
0x18000b907  nop
0x18000b908  lea     rcx, [rsp+28h+arg_8]; this
0x18000b90d  call    ??1CAutoFreeLibrary@@QEAA@XZ; CAutoFreeLibrary::~CAutoFreeLibrary(void)
0x18000b912  mov     al, 1
0x18000b914  jmp     short loc_18000B951
0x18000b916  lea     rax, WPP_GLOBAL_Control
0x18000b91d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b924  cmp     rcx, rax
0x18000b927  jz      short loc_18000B945
0x18000b929  test    byte ptr [rcx+1Ch], 4
0x18000b92d  jz      short loc_18000B945
0x18000b92f  mov     edx, 17h
0x18000b934  lea     r8, WPP_f8138a78677f34b3e5f704385132758d_Traceguids
0x18000b93b  mov     rcx, [rcx+10h]
0x18000b93f  call    WPP_SF_
0x18000b944  nop
0x18000b945  lea     rcx, [rsp+28h+arg_8]; this
0x18000b94a  call    ??1CAutoFreeLibrary@@QEAA@XZ; CAutoFreeLibrary::~CAutoFreeLibrary(void)
0x18000b94f  xor     al, al
0x18000b951  add     rsp, 28h
0x18000b955  retn
```
