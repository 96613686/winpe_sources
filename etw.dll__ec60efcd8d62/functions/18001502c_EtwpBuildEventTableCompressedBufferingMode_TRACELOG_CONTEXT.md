# EtwpBuildEventTableCompressedBufferingMode(_TRACELOG_CONTEXT *)

- ea: `0x18001502c`
- end: `0x180015263`
- name: `?EtwpBuildEventTableCompressedBufferingMode@@YAKPEAU_TRACELOG_CONTEXT@@@Z`
- size: `567`
- prototype: `__int64 __fastcall(struct _TRACELOG_CONTEXT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800148b8`

## callees

- `0x180001ee2`
- `0x1800110b0`
- `0x180012c14`
- `0x180012cc0`
- `0x180012e10`
- `0x18001502c`
- `0x180015578`

## import_xrefs

- `ntdll!RtlDecompressBufferEx` at `0x180015183`
- `ntdll!RtlDecompressBufferEx` at `0x180015183`

## pseudocode

```c
__int64 __fastcall EtwpBuildEventTableCompressedBufferingMode(struct _TRACELOG_CONTEXT *a1)
{
  unsigned int v1; // eax
  ULONG v2; // edi
  unsigned __int64 v4; // r12
  unsigned int v5; // r14d
  struct _OVERLAPPED *i; // r8
  _DWORD *v7; // rcx
  __int64 v8; // r13
  __int64 v9; // rdx
  _DWORD *v10; // rsi
  unsigned __int64 v11; // r12
  unsigned int v12; // r15d
  void *v13; // rcx
  void *v14; // rdx
  NTSTATUS v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rax
  struct _OVERLAPPED *v19; // [rsp+20h] [rbp-20h]
  unsigned int v20; // [rsp+80h] [rbp+40h] BYREF
  unsigned int v21; // [rsp+88h] [rbp+48h] BYREF
  __int64 v22; // [rsp+90h] [rbp+50h]

  v1 = *((_DWORD *)a1 + 193);
  v2 = 0;
  if ( *((_DWORD *)a1 + 194) < v1 )
  {
    v4 = 0;
    v5 = 0;
    if ( v1 )
    {
      for ( i = (struct _OVERLAPPED *)((char *)a1 + 592); ; i = (struct _OVERLAPPED *)((char *)a1 + 592) )
      {
        v7 = (_DWORD *)*((_QWORD *)a1 + 102);
        v20 = 0;
        v8 = *((_QWORD *)a1 + 100) + 432LL * (int)v5;
        v9 = 16LL * (v5 % *v7);
        v22 = v9;
        v7[(unsigned __int64)v9 / 4 + 2] = -1;
        v10 = *(_DWORD **)(*((_QWORD *)a1 + 102) + v9 + 16);
        *(_QWORD *)(v8 + 16) = v4;
        EtwpSynchReadFile(*((HANDLE *)a1 + 78), v10, 0x48u, &v20, i, v4);
        if ( v20 != 72 )
          break;
        if ( !EtwpValidateBuffer(a1, (struct _WMI_BUFFER_HEADER *)v10) )
          return 1392;
        *(_DWORD *)(v8 + 24) = *v10;
        v11 = v20 + v4;
        v12 = *v10 - v20;
        v13 = (void *)*((_QWORD *)a1 + 78);
        v19 = (struct _OVERLAPPED *)((char *)a1 + 592);
        if ( (v10[13] & 0x40) != 0 )
        {
          v14 = (void *)*((_QWORD *)a1 + 81);
          v21 = 0;
          EtwpSynchReadFile(v13, v14, v12, &v20, v19, v11);
          if ( v20 != v12 )
            return v2;
          v15 = RtlDecompressBufferEx(
                  *((unsigned __int16 *)a1 + 277),
                  v10 + 18,
                  (unsigned int)(v10[12] - 72),
                  *((_QWORD *)a1 + 81),
                  v20,
                  &v21,
                  *((_QWORD *)a1 + 82));
          v2 = RtlNtStatusToDosError_0(v15);
          if ( v2 )
            return v2;
          v16 = (unsigned int)v10[12];
          *((_WORD *)v10 + 26) &= ~0x40u;
          if ( v16 != v21 + 72LL )
            return 1392;
          *v10 = v21 + 72;
          v17 = v20;
        }
        else
        {
          EtwpSynchReadFile(v13, v10 + 18, v12, &v20, v19, v11);
          v17 = v20;
          if ( v20 != v12 )
            return v2;
        }
        v21 = 72;
        v4 = v17 + v11;
        if ( EtwpGetNextEvent((struct _WMI_BUFFER_HEADER *)v10, a1, &v21, (struct _ETW_EVENT_INFO *)(v8 + 40)) )
        {
          if ( (*((_DWORD *)a1 + 8) & 0x10000000) != 0 )
            EtwpUpdateBufferEntryQpcDelta(a1, (struct _TRACE_BUFFER_LIST_ENTRY *)v8);
          *(_DWORD *)(v8 + 12) = v21;
          *(_DWORD *)(v8 + 8) = v5;
          EtwpInsertBuffer(a1, (struct _TRACE_BUFFER_LIST_ENTRY *)v8);
          *(_DWORD *)(*((_QWORD *)a1 + 102) + v22 + 8) = v5;
        }
        if ( ++v5 >= *((_DWORD *)a1 + 193) )
          return v2;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18001502c  mov     [rsp-38h+arg_18], rbx
0x180015031  push    rbp
0x180015032  push    rsi
0x180015033  push    rdi
0x180015034  push    r12
0x180015036  push    r13
0x180015038  push    r14
0x18001503a  push    r15
0x18001503c  mov     rbp, rsp
0x18001503f  sub     rsp, 40h
0x180015043  mov     eax, [rcx+304h]
0x180015049  xor     edi, edi
0x18001504b  mov     rbx, rcx
0x18001504e  cmp     [rcx+308h], eax
0x180015054  jnb     loc_180015249
0x18001505a  xor     r12d, r12d
0x18001505d  xor     r14d, r14d
0x180015060  test    eax, eax
0x180015062  jz      loc_180015249
0x180015068  lea     r8, [rcx+250h]
0x18001506f  mov     rcx, [rbx+330h]
0x180015076  lea     r9, [rbp+arg_0]; unsigned int *
0x18001507a  mov     [rbp+arg_0], 0
0x180015081  xor     edx, edx
0x180015083  movsxd  rax, r14d
0x180015086  imul    r13, rax, 1B0h
0x18001508d  mov     eax, r14d
0x180015090  mov     [rsp+40h+var_18], r12; unsigned __int64
0x180015095  div     dword ptr [rcx]
0x180015097  add     r13, [rbx+320h]
0x18001509e  shl     rdx, 4
0x1800150a2  mov     [rbp+arg_10], rdx
0x1800150a6  mov     [rsp+40h+var_20], r8; struct _OVERLAPPED *
0x1800150ab  mov     r8d, 48h ; 'H'; unsigned int
0x1800150b1  mov     dword ptr [rdx+rcx+8], 0FFFFFFFFh
0x1800150b9  mov     rax, [rbx+330h]
0x1800150c0  mov     rsi, [rax+rdx+10h]
0x1800150c5  mov     [r13+10h], r12
0x1800150c9  mov     rdx, rsi; void *
0x1800150cc  mov     rcx, [rbx+270h]; hFile
0x1800150d3  call    ?EtwpSynchReadFile@@YAHPEAX0KPEAKPEAU_OVERLAPPED@@_K@Z; EtwpSynchReadFile(void *,void *,ulong,ulong *,_OVERLAPPED *,unsigned __int64)
0x1800150d8  cmp     [rbp+arg_0], 48h ; 'H'
0x1800150dc  jnz     loc_180015249
0x1800150e2  mov     rdx, rsi; struct _WMI_BUFFER_HEADER *
0x1800150e5  mov     rcx, rbx; struct _TRACELOG_CONTEXT *
0x1800150e8  call    ?EtwpValidateBuffer@@YAEPEAU_TRACELOG_CONTEXT@@PEAU_WMI_BUFFER_HEADER@@@Z; EtwpValidateBuffer(_TRACELOG_CONTEXT *,_WMI_BUFFER_HEADER *)
0x1800150ed  test    al, al
0x1800150ef  jz      loc_180015244
0x1800150f5  mov     eax, [rsi]
0x1800150f7  lea     r9, [rbp+arg_0]; unsigned int *
0x1800150fb  mov     [r13+18h], eax
0x1800150ff  mov     eax, [rbp+arg_0]
0x180015102  mov     r15d, [rsi]
0x180015105  add     r12, rax
0x180015108  sub     r15d, [rbp+arg_0]
0x18001510c  lea     rax, [rbx+250h]
0x180015113  test    byte ptr [rsi+34h], 40h
0x180015117  mov     r8d, r15d; unsigned int
0x18001511a  mov     rcx, [rbx+270h]; hFile
0x180015121  mov     [rsp+40h+var_18], r12; unsigned __int64
0x180015126  mov     [rsp+40h+var_20], rax; struct _OVERLAPPED *
0x18001512b  jz      loc_1800151C0
0x180015131  mov     rdx, [rbx+288h]; void *
0x180015138  mov     [rbp+arg_8], 0
0x18001513f  call    ?EtwpSynchReadFile@@YAHPEAX0KPEAKPEAU_OVERLAPPED@@_K@Z; EtwpSynchReadFile(void *,void *,ulong,ulong *,_OVERLAPPED *,unsigned __int64)
0x180015144  mov     ecx, [rbp+arg_0]
0x180015147  cmp     ecx, r15d
0x18001514a  jnz     loc_180015249
0x180015150  mov     rax, [rbx+290h]
0x180015157  lea     rdx, [rsi+48h]
0x18001515b  mov     r8d, [rsi+30h]
0x18001515f  mov     r9, [rbx+288h]
0x180015166  sub     r8d, 48h ; 'H'
0x18001516a  mov     [rsp+40h+var_10], rax
0x18001516f  lea     rax, [rbp+arg_8]
0x180015173  mov     [rsp+40h+var_18], rax
0x180015178  mov     dword ptr [rsp+40h+var_20], ecx
0x18001517c  movzx   ecx, word ptr [rbx+22Ah]
0x180015183  call    cs:__imp_RtlDecompressBufferEx
0x180015189  mov     ecx, eax; Status
0x18001518b  call    RtlNtStatusToDosError_0
0x180015190  mov     edi, eax
0x180015192  test    eax, eax
0x180015194  jnz     loc_180015249
0x18001519a  mov     ecx, [rsi+30h]
0x18001519d  mov     eax, 0FFBFh
0x1800151a2  and     [rsi+34h], ax
0x1800151a6  mov     eax, [rbp+arg_8]
0x1800151a9  lea     rdx, [rax+48h]
0x1800151ad  cmp     rcx, rdx
0x1800151b0  jnz     loc_180015244
0x1800151b6  lea     ecx, [rax+48h]
0x1800151b9  mov     [rsi], ecx
0x1800151bb  mov     eax, [rbp+arg_0]
0x1800151be  jmp     short loc_1800151D1
0x1800151c0  lea     rdx, [rsi+48h]; void *
0x1800151c4  call    ?EtwpSynchReadFile@@YAHPEAX0KPEAKPEAU_OVERLAPPED@@_K@Z; EtwpSynchReadFile(void *,void *,ulong,ulong *,_OVERLAPPED *,unsigned __int64)
0x1800151c9  mov     eax, [rbp+arg_0]
0x1800151cc  cmp     eax, r15d
0x1800151cf  jnz     short loc_180015249
0x1800151d1  lea     r9, [r13+28h]; struct _ETW_EVENT_INFO *
0x1800151d5  mov     [rbp+arg_8], 48h ; 'H'
0x1800151dc  lea     r8, [rbp+arg_8]; unsigned int *
0x1800151e0  mov     rdx, rbx; struct _TRACELOG_CONTEXT *
0x1800151e3  mov     rcx, rsi; struct _WMI_BUFFER_HEADER *
0x1800151e6  add     r12, rax
0x1800151e9  call    ?EtwpGetNextEvent@@YAEPEAU_WMI_BUFFER_HEADER@@PEAU_TRACELOG_CONTEXT@@PEAKPEAU_ETW_EVENT_INFO@@@Z; EtwpGetNextEvent(_WMI_BUFFER_HEADER *,_TRACELOG_CONTEXT *,ulong *,_ETW_EVENT_INFO *)
0x1800151ee  test    al, al
0x1800151f0  jz      short loc_18001522C
0x1800151f2  test    dword ptr [rbx+20h], 10000000h
0x1800151f9  jz      short loc_180015206
0x1800151fb  mov     rdx, r13; struct _TRACE_BUFFER_LIST_ENTRY *
0x1800151fe  mov     rcx, rbx; struct _TRACELOG_CONTEXT *
0x180015201  call    ?EtwpUpdateBufferEntryQpcDelta@@YAXPEAU_TRACELOG_CONTEXT@@PEAU_TRACE_BUFFER_LIST_ENTRY@@@Z; EtwpUpdateBufferEntryQpcDelta(_TRACELOG_CONTEXT *,_TRACE_BUFFER_LIST_ENTRY *)
0x180015206  mov     eax, [rbp+arg_8]
0x180015209  mov     rdx, r13; struct _TRACE_BUFFER_LIST_ENTRY *
0x18001520c  mov     rcx, rbx; struct _TRACELOG_CONTEXT *
0x18001520f  mov     [r13+0Ch], eax
0x180015213  mov     [r13+8], r14d
0x180015217  call    ?EtwpInsertBuffer@@YAXPEAU_TRACELOG_CONTEXT@@PEAU_TRACE_BUFFER_LIST_ENTRY@@@Z; EtwpInsertBuffer(_TRACELOG_CONTEXT *,_TRACE_BUFFER_LIST_ENTRY *)
0x18001521c  mov     rax, [rbx+330h]
0x180015223  mov     rcx, [rbp+arg_10]
0x180015227  mov     [rax+rcx+8], r14d
0x18001522c  inc     r14d
0x18001522f  cmp     r14d, [rbx+304h]
0x180015236  jnb     short loc_180015249
0x180015238  lea     r8, [rbx+250h]
0x18001523f  jmp     loc_18001506F
0x180015244  mov     edi, 570h
0x180015249  mov     rbx, [rsp+40h+arg_18]
0x180015251  mov     eax, edi
0x180015253  add     rsp, 40h
0x180015257  pop     r15
0x180015259  pop     r14
0x18001525b  pop     r13
0x18001525d  pop     r12
0x18001525f  pop     rdi
0x180015260  pop     rsi
0x180015261  pop     rbp
0x180015262  retn
```
