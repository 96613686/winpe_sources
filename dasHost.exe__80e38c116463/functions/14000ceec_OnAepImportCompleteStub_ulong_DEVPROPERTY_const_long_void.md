# OnAepImportCompleteStub(ulong,_DEVPROPERTY * const,long,void *)

- ea: `0x14000ceec`
- end: `0x14000d01a`
- name: `?OnAepImportCompleteStub@@YAJKQEAU_DEVPROPERTY@@JPEAX@Z`
- size: `302`
- prototype: `__int64 __fastcall(unsigned int, struct _DEVPROPERTY *const, int, void *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000d1f0`
- `0x14000d590`
- `0x1400187a0`

## callees

- `0x140008eec`
- `0x140008f88`
- `0x14000ceec`
- `0x140019c5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000cfd3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000cfd3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000cf44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000cf44`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000cfb6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000cfb6`

## pseudocode

```c
__int64 __fastcall OnAepImportCompleteStub(unsigned int a1, struct _DEVPROPERTY *const a2, int a3, void *a4)
{
  int v7; // ebx
  unsigned int *v8; // rax
  struct _RPC_ASYNC_STATE *v9; // rcx
  RPC_STATUS v10; // eax
  int v11; // edx
  int v12; // r8d
  int v14; // [rsp+28h] [rbp-40h]
  int Reply; // [rsp+80h] [rbp+18h] BYREF

  Reply = a3;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)a2,
      a3,
      20,
      &WPP_344ea40e1f873519cdb41334aa7e6fb5_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)a4 + 1);
  if ( *((_DWORD *)a4 + 20) )
  {
    v7 = -2147418113;
  }
  else
  {
    v7 = 0;
    **((_DWORD **)a4 + 12) = 0;
    **((_QWORD **)a4 + 13) = 0;
    if ( a1 && a2 )
    {
      v7 = MidlCopyDevProperties(a2, a1, *((struct _DEVPROPERTY ***)a4 + 13));
      v8 = (unsigned int *)*((_QWORD *)a4 + 12);
      if ( v7 >= 0 )
      {
        *v8 = a1;
      }
      else
      {
        Reply = v7;
        *v8 = 0;
        **((_QWORD **)a4 + 13) = 0;
      }
    }
    v9 = (struct _RPC_ASYNC_STATE *)*((_QWORD *)a4 + 2);
    *((_DWORD *)a4 + 20) = 1;
    v10 = RpcAsyncCompleteCall(v9, &Reply);
    if ( v10 )
    {
      if ( v10 < 0 )
        v7 = v10;
      else
        v7 = (unsigned __int16)v10 | 0x80010000;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)a4 + 1);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v11,
      v12,
      21,
      &WPP_344ea40e1f873519cdb41334aa7e6fb5_Traceguids,
      v14,
      v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000ceec  mov     rax, rsp
0x14000ceef  mov     [rax+8], rbx
0x14000cef3  mov     [rax+10h], rbp
0x14000cef7  mov     [rax+18h], r8d
0x14000cefb  push    rsi
0x14000cefc  push    rdi
0x14000cefd  push    r12
0x14000ceff  push    r13
0x14000cf01  push    r14
0x14000cf03  sub     rsp, 40h
0x14000cf07  mov     rdi, r9
0x14000cf0a  mov     r14, rdx
0x14000cf0d  mov     esi, ecx
0x14000cf0f  lea     r13, WPP_RECORDER_INITIALIZED
0x14000cf16  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000cf1d  lea     r12, WPP_344ea40e1f873519cdb41334aa7e6fb5_Traceguids
0x14000cf24  jz      short loc_14000CF40
0x14000cf26  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cf2d  mov     r9d, 14h; int
0x14000cf33  mov     [rax-48h], r12
0x14000cf37  mov     rcx, [rcx+28h]; int
0x14000cf3b  call    WPP_RECORDER_SF_s
0x14000cf40  lea     rcx, [rdi+28h]; lpCriticalSection
0x14000cf44  call    cs:__imp_EnterCriticalSection
0x14000cf4a  cmp     dword ptr [rdi+50h], 0
0x14000cf4e  jz      short loc_14000CF57
0x14000cf50  mov     ebx, 8000FFFFh
0x14000cf55  jmp     short loc_14000CFCF
0x14000cf57  mov     rax, [rdi+60h]
0x14000cf5b  xor     ebx, ebx
0x14000cf5d  mov     [rax], ebx
0x14000cf5f  mov     rax, [rdi+68h]
0x14000cf63  mov     [rax], rbx
0x14000cf66  test    esi, esi
0x14000cf68  jz      short loc_14000CFA3
0x14000cf6a  test    r14, r14
0x14000cf6d  jz      short loc_14000CFA3
0x14000cf6f  mov     r8, [rdi+68h]; struct _DEVPROPERTY **
0x14000cf73  mov     edx, esi; unsigned int
0x14000cf75  mov     rcx, r14; struct _DEVPROPERTY *
0x14000cf78  call    ?MidlCopyDevProperties@@YAJPEAU_DEVPROPERTY@@KPEAPEAU1@@Z; MidlCopyDevProperties(_DEVPROPERTY *,ulong,_DEVPROPERTY * *)
0x14000cf7d  mov     ebx, eax
0x14000cf7f  mov     rax, [rdi+60h]
0x14000cf83  test    ebx, ebx
0x14000cf85  jns     short loc_14000CFA1
0x14000cf87  mov     [rsp+68h+Reply], ebx
0x14000cf8e  mov     dword ptr [rax], 0
0x14000cf94  mov     rcx, [rdi+68h]
0x14000cf98  mov     qword ptr [rcx], 0
0x14000cf9f  jmp     short loc_14000CFA3
0x14000cfa1  mov     [rax], esi
0x14000cfa3  mov     rcx, [rdi+10h]; pAsync
0x14000cfa7  lea     rdx, [rsp+68h+Reply]; Reply
0x14000cfaf  mov     dword ptr [rdi+50h], 1
0x14000cfb6  call    cs:__imp_RpcAsyncCompleteCall
0x14000cfbc  test    eax, eax
0x14000cfbe  jz      short loc_14000CFCF
0x14000cfc0  js      short loc_14000CFCD
0x14000cfc2  movzx   ebx, ax
0x14000cfc5  or      ebx, 80010000h
0x14000cfcb  jmp     short loc_14000CFCF
0x14000cfcd  mov     ebx, eax
0x14000cfcf  lea     rcx, [rdi+28h]; lpCriticalSection
0x14000cfd3  call    cs:__imp_LeaveCriticalSection
0x14000cfd9  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000cfe0  jz      short loc_14000D001
0x14000cfe2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cfe9  mov     r9d, 15h; int
0x14000cfef  mov     dword ptr [rsp+68h+var_38], ebx; char
0x14000cff3  mov     [rsp+68h+MessageGuid], r12; MessageGuid
0x14000cff8  mov     rcx, [rcx+28h]; int
0x14000cffc  call    WPP_RECORDER_SF_sd
0x14000d001  mov     rbp, [rsp+68h+arg_8]
0x14000d006  mov     eax, ebx
0x14000d008  mov     rbx, [rsp+68h+arg_0]
0x14000d00d  add     rsp, 40h
0x14000d011  pop     r14
0x14000d013  pop     r13
0x14000d015  pop     r12
0x14000d017  pop     rdi
0x14000d018  pop     rsi
0x14000d019  retn
```
