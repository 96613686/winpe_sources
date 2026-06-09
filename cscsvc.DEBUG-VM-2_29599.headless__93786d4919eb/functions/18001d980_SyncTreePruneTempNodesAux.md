# SyncTreePruneTempNodesAux

- ea: `0x18001d980`
- end: `0x18001dc01`
- name: `SyncTreePruneTempNodesAux`
- size: `641`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001d980`
- `0x18007479c`

## callees

- `0x180004c40`
- `0x18001d980`
- `0x1800345c0`
- `0x180035a58`
- `0x1800360c0`
- `0x180036394`
- `0x18004ff34`
- `0x1800742ec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001da2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001da2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001da21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001da21`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001dbf0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001dbf0`

## string_xrefs

- `0x18001db05`: `SyncTreePruneTempNodesAux: Deleting node 0x%p (%ws)`
- `0x18001db5a`: `SyncTreePruneTempNodesAux: 0x%x`
- `0x18001db8d`: `SyncTreePruneTempNodesAux: Context: 0x%p Node: 0x%p`

## pseudocode

```c
__int64 __fastcall SyncTreePruneTempNodesAux(__int64 a1, int **a2, __int64 a3)
{
  unsigned int v3; // ebp
  __int64 v6; // rbx
  int *v7; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v10; // rax
  __int64 v11; // r15
  __int64 v12; // rbx
  __int64 v13; // rax
  struct _RTL_CRITICAL_SECTION *History; // rbx

  v3 = 0;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    SyncTraceOutputInternal(L"SyncTreePruneTempNodesAux: Context: 0x%p Node: 0x%p", a1, a2);
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 12), 24, WPP_423b4d92c1c83c8cb080e269378a479c_Traceguids, a1, a2);
  }
  if ( *a2 )
  {
    v6 = *((_QWORD *)*a2 + 1);
    if ( !v6 )
    {
LABEL_6:
      v7 = *a2;
      if ( (**a2 & 0x20000000) != 0 )
      {
        if ( *((_QWORD *)v7 + 1) )
        {
          LOBYTE(a3) = 1;
          v3 = SyncTreeCommitTempNode(a1, a2, a3);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
          {
            SyncTraceOutputInternal(L"SyncTreePruneTempNodesAux: Deleting node 0x%p (%ws)", *a2, v7 + 36);
            if ( (*v7 & 0x20000000) != 0 )
            {
              v13 = 36;
            }
            else
            {
              v13 = 34;
              if ( *v7 < 0 )
                v13 = 9;
            }
            WPP_SF_qS(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              25,
              (unsigned int)WPP_423b4d92c1c83c8cb080e269378a479c_Traceguids,
              (_DWORD)v7,
              (__int64)&v7[v13]);
          }
          if ( (*v7 & 0x40000000) != 0 )
          {
            History = (struct _RTL_CRITICAL_SECTION *)SyncItemTraceFindHistory(v7, 0);
            SyncFree(History[1].OwningThread);
            DeleteCriticalSection(History);
            *v7 &= ~0x40000000u;
          }
          ++NumFree;
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v7);
          *a2 = 0;
        }
      }
      goto LABEL_13;
    }
    while ( 1 )
    {
      v10 = *(_QWORD *)(v6 + 16);
      if ( !v10 )
        break;
      v11 = *(_QWORD *)(v10 + 16);
      v3 = SyncTreePruneTempNodesAux(a1);
      if ( v3 )
        goto LABEL_13;
      if ( *(_QWORD *)(v6 + 16) )
        v6 = *(_QWORD *)(v6 + 16);
      else
        *(_QWORD *)(v6 + 16) = v11;
    }
    v12 = *(_QWORD *)(*((_QWORD *)*a2 + 1) + 16LL);
    v3 = SyncTreePruneTempNodesAux(a1);
    if ( !v3 )
    {
      if ( !*((_QWORD *)*a2 + 1) )
        *((_QWORD *)*a2 + 1) = v12;
      goto LABEL_6;
    }
  }
LABEL_13:
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncTreePruneTempNodesAux: 0x%x", v3);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 26, WPP_423b4d92c1c83c8cb080e269378a479c_Traceguids, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x18001d980  push    rbp
0x18001d982  sub     rsp, 40h
0x18001d986  mov     [rsp+48h+arg_8], rsi
0x18001d98b  xor     ebp, ebp
0x18001d98d  mov     [rsp+48h+arg_18], r12
0x18001d992  mov     rsi, rdx
0x18001d995  mov     [rsp+48h+var_10], r14
0x18001d99a  mov     r14, rcx
0x18001d99d  mov     rax, cs:WPP_GLOBAL_Control
0x18001d9a4  lea     r12, WPP_GLOBAL_Control
0x18001d9ab  cmp     rax, r12
0x18001d9ae  jz      short loc_18001D9BA
0x18001d9b0  test    byte ptr [rax+6Ch], 4
0x18001d9b4  jnz     loc_18001DB8A
0x18001d9ba  mov     rax, [rsi]
0x18001d9bd  test    rax, rax
0x18001d9c0  jz      loc_18001DA4B
0x18001d9c6  mov     [rsp+48h+arg_0], rbx
0x18001d9cb  mov     rbx, [rax+8]
0x18001d9cf  mov     [rsp+48h+arg_10], rdi
0x18001d9d4  mov     [rsp+48h+var_18], r15
0x18001d9d9  test    rbx, rbx
0x18001d9dc  jnz     loc_18001DA80
0x18001d9e2  mov     rdi, [rsi]
0x18001d9e5  test    dword ptr [rdi], 20000000h
0x18001d9eb  jz      short loc_18001DA3C
0x18001d9ed  cmp     qword ptr [rdi+8], 0
0x18001d9f2  jnz     loc_18001DAE6
0x18001d9f8  mov     rax, cs:WPP_GLOBAL_Control
0x18001d9ff  cmp     rax, r12
0x18001da02  jz      short loc_18001DA0E
0x18001da04  test    byte ptr [rax+6Ch], 2
0x18001da08  jnz     loc_18001DAFB
0x18001da0e  test    dword ptr [rdi], 40000000h
0x18001da14  jnz     loc_18001DBD7
0x18001da1a  inc     cs:NumFree
0x18001da21  call    cs:__imp_GetProcessHeap
0x18001da27  mov     r8, rdi; lpMem
0x18001da2a  xor     edx, edx; dwFlags
0x18001da2c  mov     rcx, rax; hHeap
0x18001da2f  call    cs:__imp_HeapFree
0x18001da35  mov     qword ptr [rsi], 0
0x18001da3c  mov     rdi, [rsp+48h+arg_10]
0x18001da41  mov     r15, [rsp+48h+var_18]
0x18001da46  mov     rbx, [rsp+48h+arg_0]
0x18001da4b  mov     rax, cs:WPP_GLOBAL_Control
0x18001da52  mov     r14, [rsp+48h+var_10]
0x18001da57  cmp     rax, r12
0x18001da5a  mov     r12, [rsp+48h+arg_18]
0x18001da5f  mov     rsi, [rsp+48h+arg_8]
0x18001da64  jz      short loc_18001DA70
0x18001da66  test    byte ptr [rax+6Ch], 8
0x18001da6a  jnz     loc_18001DB58
0x18001da70  mov     eax, ebp
0x18001da72  add     rsp, 40h
0x18001da76  pop     rbp
0x18001da77  retn
0x18001da80  mov     rax, [rbx+10h]
0x18001da84  mov     rcx, r14
0x18001da87  test    rax, rax
0x18001da8a  jz      short loc_18001DAB2
0x18001da8c  mov     r15, [rax+10h]
0x18001da90  lea     rdx, [rbx+10h]
0x18001da94  call    SyncTreePruneTempNodesAux
0x18001da99  mov     ebp, eax
0x18001da9b  test    eax, eax
0x18001da9d  jnz     short loc_18001DA3C
0x18001da9f  mov     rax, [rbx+10h]
0x18001daa3  test    rax, rax
0x18001daa6  jnz     loc_18001DBC5
0x18001daac  mov     [rbx+10h], r15
0x18001dab0  jmp     short loc_18001DA80
0x18001dab2  mov     rdx, [rsi]
0x18001dab5  add     rdx, 8
0x18001dab9  mov     rax, [rdx]
0x18001dabc  mov     rbx, [rax+10h]
0x18001dac0  call    SyncTreePruneTempNodesAux
0x18001dac5  mov     ebp, eax
0x18001dac7  test    eax, eax
0x18001dac9  jnz     loc_18001DA3C
0x18001dacf  mov     rax, [rsi]
0x18001dad2  cmp     qword ptr [rax+8], 0
0x18001dad7  jnz     loc_18001D9E2
0x18001dadd  mov     [rax+8], rbx
0x18001dae1  jmp     loc_18001D9E2
0x18001dae6  mov     r8b, 1
0x18001dae9  mov     rdx, rsi
0x18001daec  mov     rcx, r14
0x18001daef  call    SyncTreeCommitTempNode
0x18001daf4  mov     ebp, eax
0x18001daf6  jmp     loc_18001DA3C
0x18001dafb  lea     r8, [rdi+90h]
0x18001db02  mov     rdx, rdi
0x18001db05  lea     rcx, aSynctreeprunet_2; "SyncTreePruneTempNodesAux: Deleting nod"...
0x18001db0c  call    SyncTraceOutputInternal
0x18001db11  mov     ecx, [rdi]
0x18001db13  bt      ecx, 1Dh
0x18001db17  jb      loc_18001DBCD
0x18001db1d  test    ecx, ecx
0x18001db1f  mov     eax, 88h
0x18001db24  mov     edx, 24h ; '$'
0x18001db29  cmovs   eax, edx
0x18001db2c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db33  lea     r8, WPP_423b4d92c1c83c8cb080e269378a479c_Traceguids
0x18001db3a  add     rax, rdi
0x18001db3d  mov     edx, 19h
0x18001db42  mov     r9, rdi
0x18001db45  mov     [rsp+48h+var_28], rax
0x18001db4a  mov     rcx, [rcx+60h]
0x18001db4e  call    WPP_SF_qS
0x18001db53  jmp     loc_18001DA0E
0x18001db58  mov     edx, ebp
0x18001db5a  lea     rcx, aSynctreeprunet_0; "SyncTreePruneTempNodesAux: 0x%x"
0x18001db61  call    SyncTraceOutputInternal
0x18001db66  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db6d  lea     r8, WPP_423b4d92c1c83c8cb080e269378a479c_Traceguids
0x18001db74  mov     edx, 1Ah
0x18001db79  mov     r9d, ebp
0x18001db7c  mov     rcx, [rcx+60h]
0x18001db80  call    WPP_SF_d
0x18001db85  jmp     loc_18001DA70
0x18001db8a  mov     r8, rsi
0x18001db8d  lea     rcx, aSynctreeprunet; "SyncTreePruneTempNodesAux: Context: 0x%"...
0x18001db94  mov     rdx, r14
0x18001db97  call    SyncTraceOutputInternal
0x18001db9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dba3  lea     r8, WPP_423b4d92c1c83c8cb080e269378a479c_Traceguids
0x18001dbaa  mov     edx, 18h
0x18001dbaf  mov     [rsp+48h+var_28], rsi
0x18001dbb4  mov     r9, r14
0x18001dbb7  mov     rcx, [rcx+60h]
0x18001dbbb  call    WPP_SF_qq
0x18001dbc0  jmp     loc_18001D9BA
0x18001dbc5  mov     rbx, rax
0x18001dbc8  jmp     loc_18001DA80
0x18001dbcd  mov     eax, 90h
0x18001dbd2  jmp     loc_18001DB2C
0x18001dbd7  xor     edx, edx
0x18001dbd9  mov     rcx, rdi
0x18001dbdc  call    SyncItemTraceFindHistory
0x18001dbe1  mov     rbx, rax
0x18001dbe4  mov     rcx, [rax+38h]
0x18001dbe8  call    SyncFree
0x18001dbed  mov     rcx, rbx; lpCriticalSection
0x18001dbf0  call    cs:__imp_DeleteCriticalSection
0x18001dbf6  and     dword ptr [rdi], 0BFFFFFFFh
0x18001dbfc  jmp     loc_18001DA1A
```
