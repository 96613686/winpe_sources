# CreateIpv4TransportInfo(ulong *,uchar * *)

- ea: `0x1800445b0`
- end: `0x1800446b8`
- name: `?CreateIpv4TransportInfo@@YAKPEAKPEAPEAE@Z`
- size: `264`
- prototype: `__int64 __fastcall(unsigned int *, unsigned __int8 **, __int64, void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003bd5c`

## callees

- `0x1800445b0`
- `0x18004583c`
- `0x180045ad4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004462d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004462d`
- `KERNEL32!GetProcessHeap` at `0x180044619`
- `KERNEL32!GetProcessHeap` at `0x180044619`

## string_xrefs

- `0x180044609`: `CreateIpv4TransportInfo`

## pseudocode

```c
__int64 __fastcall CreateIpv4TransportInfo(
        unsigned int *a1,
        unsigned __int8 **a2,
        __int64 a3,
        void (*a4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))
{
  HANDLE ProcessHeap; // rax
  unsigned int v7; // ebx
  char *v8; // rax
  _DWORD *v9; // rcx
  __int64 v11; // [rsp+20h] [rbp-48h] BYREF
  __int128 v12; // [rsp+28h] [rbp-40h]
  __int128 v13; // [rsp+38h] [rbp-30h]
  __int64 v14; // [rsp+48h] [rbp-20h]
  int v15; // [rsp+50h] [rbp-18h]
  int v16; // [rsp+54h] [rbp-14h]
  unsigned int v17; // [rsp+80h] [rbp+18h] BYREF

  v17 = 0;
  v12 = 0;
  v11 = 0;
  v13 = 0;
  v14 = 0;
  v15 = -1;
  v16 = 0;
  if ( *((_QWORD *)&xmmword_180071090 + 1) )
    EtwFuncEntryExitTracer::Initialize((EtwFuncEntryExitTracer *)&v11, L"CreateIpv4TransportInfo", &v17, a4);
  ProcessHeap = GetProcessHeap();
  v7 = 8;
  v8 = (char *)HeapAlloc(ProcessHeap, 8u, 0x2Cu);
  if ( v8 )
  {
    *(_DWORD *)v8 = 0;
    *(_QWORD *)(v8 + 28) = 0;
    *(_QWORD *)(v8 + 36) = 0;
    *(_DWORD *)v8 = 1;
    *((_DWORD *)v8 + 1) = 44;
    *((_DWORD *)v8 + 2) = 1;
    v9 = (_DWORD *)((unsigned __int64)(v8 + 35) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_DWORD *)v8 + 3) = -65533;
    *((_DWORD *)v8 + 4) = 8;
    *((_DWORD *)v8 + 5) = 1;
    *((_DWORD *)v8 + 6) = (((_DWORD)v8 + 35) & 0xFFFFFFF8) - (_DWORD)v8;
    *v9 = 0;
    v9[1] = 1;
    *a2 = (unsigned __int8 *)v8;
    *a1 = 44;
    v7 = 0;
  }
  else
  {
    *a2 = 0;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v11);
  return v7;
}

```

## disassembly

```asm
0x1800445b0  mov     rax, rsp
0x1800445b3  mov     [rax+8], rbx
0x1800445b7  mov     [rax+10h], rsi
0x1800445bb  push    rdi
0x1800445bc  sub     rsp, 60h
0x1800445c0  mov     rdi, rdx
0x1800445c3  mov     rsi, rcx
0x1800445c6  mov     dword ptr [rax+18h], 0
0x1800445cd  xorps   xmm0, xmm0
0x1800445d0  movdqu  xmmword ptr [rax-40h], xmm0
0x1800445d5  mov     qword ptr [rax-48h], 0
0x1800445dd  xorps   xmm1, xmm1
0x1800445e0  movdqu  xmmword ptr [rax-30h], xmm1
0x1800445e5  mov     qword ptr [rax-20h], 0
0x1800445ed  mov     dword ptr [rax-18h], 0FFFFFFFFh
0x1800445f4  mov     dword ptr [rax-14h], 0
0x1800445fb  cmp     qword ptr cs:xmmword_180071090+8, 0
0x180044603  jz      short loc_180044619
0x180044605  lea     r8, [rax+18h]; unsigned int *
0x180044609  lea     rdx, aCreateipv4tran; "CreateIpv4TransportInfo"
0x180044610  lea     rcx, [rax-48h]; this
0x180044614  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180044619  call    cs:__imp_GetProcessHeap
0x18004461f  mov     rcx, rax; hHeap
0x180044622  mov     ebx, 8
0x180044627  lea     r8d, [rbx+24h]; dwBytes
0x18004462b  mov     edx, ebx; dwFlags
0x18004462d  call    cs:__imp_HeapAlloc
0x180044633  mov     rdx, rax
0x180044636  test    rax, rax
0x180044639  jnz     short loc_180044640
0x18004463b  mov     [rdi], rax
0x18004463e  jmp     short loc_18004469C
0x180044640  mov     dword ptr [rax], 0
0x180044646  mov     qword ptr [rax+1Ch], 0
0x18004464e  mov     qword ptr [rax+24h], 0
0x180044656  mov     r8d, 1
0x18004465c  mov     [rax], r8d
0x18004465f  mov     dword ptr [rax+4], 2Ch ; ','
0x180044666  mov     [rax+8], r8d
0x18004466a  lea     rcx, [rax+23h]
0x18004466e  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180044672  mov     dword ptr [rax+0Ch], 0FFFF0003h
0x180044679  mov     [rax+10h], ebx
0x18004467c  mov     [rax+14h], r8d
0x180044680  mov     eax, ecx
0x180044682  sub     eax, edx
0x180044684  mov     [rdx+18h], eax
0x180044687  mov     dword ptr [rcx], 0
0x18004468d  mov     [rcx+4], r8d
0x180044691  mov     [rdi], rdx
0x180044694  mov     dword ptr [rsi], 2Ch ; ','
0x18004469a  xor     ebx, ebx
0x18004469c  lea     rcx, [rsp+68h+var_48]; this
0x1800446a1  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800446a6  mov     eax, ebx
0x1800446a8  mov     rbx, [rsp+68h+arg_0]
0x1800446ad  mov     rsi, [rsp+68h+arg_8]
0x1800446b2  add     rsp, 60h
0x1800446b6  pop     rdi
0x1800446b7  retn
```
