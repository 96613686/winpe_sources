# SpQueryLsaModeContextAttributes(unsigned __int64,ulong,void *)

- ea: `0x180009940`
- end: `0x180009a59`
- name: `?SpQueryLsaModeContextAttributes@@YAJ_KKPEAX@Z`
- size: `281`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x180009940`
- `0x180009e00`
- `0x18000a020`
- `0x18004abb8`
- `0x18004aca4`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009a24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009a24`

## pseudocode

```c
__int64 __fastcall SpQueryLsaModeContextAttributes(__int64 a1, int a2, void *a3)
{
  int v6; // eax
  void *v7; // rdi
  unsigned int v8; // ebx
  DWORD CurrentProcessId; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  void *v13; // [rsp+40h] [rbp-48h] BYREF
  BOOL v14; // [rsp+A8h] [rbp+20h] BYREF

  v13 = 0;
  v14 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids, a1, a2);
  v6 = SspContextReferenceContext(a1, 0, &v13);
  v7 = v13;
  v8 = v6;
  if ( v6 >= 0 )
  {
    if ( a2 == 30 )
    {
      v14 = 0;
      v14 = *((_DWORD *)v13 + 18) < 3;
      v8 = ((__int64 (__fastcall *)(_QWORD, __int64, void *, BOOL *))LsaFunctions->CopyToClientBuffer)(0, 4, a3, &v14);
    }
    else
    {
      v8 = -1073741637;
    }
  }
  if ( v7 )
    SspContextDereferenceContext(v7);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    CurrentProcessId = GetCurrentProcessId();
    WPP_SF_DDqD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, v8, CurrentProcessId, a1, a2);
  }
  return v8;
}

```

## disassembly

```asm
0x180009940  mov     rax, rsp
0x180009943  push    rbx
0x180009944  push    rbp
0x180009945  push    rsi
0x180009946  push    rdi
0x180009947  push    r13
0x180009949  push    r14
0x18000994b  sub     rsp, 58h
0x18000994f  mov     r14, r8
0x180009952  mov     qword ptr [rax-48h], 0
0x18000995a  mov     esi, edx
0x18000995c  mov     dword ptr [rax+20h], 0
0x180009963  mov     rbp, rcx
0x180009966  mov     rcx, cs:WPP_GLOBAL_Control
0x18000996d  lea     r13, WPP_GLOBAL_Control
0x180009974  cmp     rcx, r13
0x180009977  jz      short loc_18000999D
0x180009979  test    dword ptr [rcx+1Ch], 100h
0x180009980  jz      short loc_18000999D
0x180009982  mov     rcx, [rcx+10h]
0x180009986  lea     r8, WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids
0x18000998d  mov     edx, 0Ah
0x180009992  mov     [rax-68h], esi
0x180009995  mov     r9, rbp
0x180009998  call    WPP_SF_qD
0x18000999d  lea     r8, [rsp+88h+var_48]
0x1800099a2  xor     edx, edx
0x1800099a4  mov     rcx, rbp
0x1800099a7  call    SspContextReferenceContext
0x1800099ac  mov     rdi, [rsp+88h+var_48]
0x1800099b1  mov     ebx, eax
0x1800099b3  test    eax, eax
0x1800099b5  js      short loc_180009A02
0x1800099b7  cmp     esi, 1Eh
0x1800099ba  jz      short loc_1800099C3
0x1800099bc  mov     ebx, 0C00000BBh
0x1800099c1  jmp     short loc_180009A02
0x1800099c3  xor     eax, eax
0x1800099c5  mov     [rsp+88h+arg_18], 0
0x1800099d0  cmp     dword ptr [rdi+48h], 3
0x1800099d4  lea     r9, [rsp+88h+arg_18]
0x1800099dc  mov     r8, r14
0x1800099df  mov     edx, 4
0x1800099e4  setl    al
0x1800099e7  xor     ecx, ecx
0x1800099e9  mov     [rsp+88h+arg_18], eax
0x1800099f0  mov     rax, cs:LsaFunctions
0x1800099f7  mov     rax, [rax+48h]
0x1800099fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a00  mov     ebx, eax
0x180009a02  test    rdi, rdi
0x180009a05  jz      short loc_180009A0F
0x180009a07  mov     rcx, rdi; void *
0x180009a0a  call    SspContextDereferenceContext
0x180009a0f  mov     rax, cs:WPP_GLOBAL_Control
0x180009a16  cmp     rax, r13
0x180009a19  jz      short loc_180009A4A
0x180009a1b  test    dword ptr [rax+1Ch], 100h
0x180009a22  jz      short loc_180009A4A
0x180009a24  call    cs:__imp_GetCurrentProcessId
0x180009a2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a31  mov     r9d, ebx
0x180009a34  mov     [rsp+88h+var_58], esi
0x180009a38  mov     [rsp+88h+var_60], rbp
0x180009a3d  mov     [rsp+88h+var_68], eax
0x180009a41  mov     rcx, [rcx+10h]
0x180009a45  call    WPP_SF_DDqD
0x180009a4a  mov     eax, ebx
0x180009a4c  add     rsp, 58h
0x180009a50  pop     r14
0x180009a52  pop     r13
0x180009a54  pop     rdi
0x180009a55  pop     rsi
0x180009a56  pop     rbp
0x180009a57  pop     rbx
0x180009a58  retn
```
