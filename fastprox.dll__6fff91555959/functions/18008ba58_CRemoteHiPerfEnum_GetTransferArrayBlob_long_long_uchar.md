# CRemoteHiPerfEnum::GetTransferArrayBlob(long *,long *,uchar * *)

- ea: `0x18008ba58`
- end: `0x18008bc6b`
- name: `?GetTransferArrayBlob@CRemoteHiPerfEnum@@QEAAJPEAJ0PEAPEAE@Z`
- size: `531`
- prototype: `__int64 __fastcall(CRemoteHiPerfEnum *__hidden this, int *, int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008c4c8`

## callees

- `0x180037120`
- `0x180048df0`
- `0x180048f08`
- `0x180048f60`
- `0x180071820`
- `0x180078e60`
- `0x18008ba58`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008bb32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008bb32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008bbca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008bbca`
- `wbemcomn!GetMemLogObject` at `0x18008bc05`
- `wbemcomn!GetMemLogObject` at `0x18008bc05`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18008bac9`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18008badf`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18008bb17`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18008bb5f`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18008bac9`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18008badf`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18008bb17`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18008bb5f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008bc10`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008bc10`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x18008baf2`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x18008bb6e`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x18008baf2`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x18008bb6e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRemoteHiPerfEnum::GetTransferArrayBlob(
        CRemoteHiPerfEnum *this,
        int *a2,
        int *a3,
        unsigned __int8 **a4)
{
  int TransferArrayBlob; // ebx
  int v6; // edi
  unsigned __int8 *v7; // rsi
  int v8; // r12d
  unsigned int v9; // ebp
  CWbemInstance ***v10; // rax
  int ActualTransferBlobSize; // eax
  int v12; // r15d
  unsigned __int8 *v13; // rax
  unsigned int v14; // ebp
  CWbemInstance *v15; // r12
  CMemoryLog *MemLogObject; // rax
  char *v18; // [rsp+20h] [rbp-58h] BYREF
  int v20; // [rsp+80h] [rbp+8h] BYREF
  unsigned __int8 *v21; // [rsp+88h] [rbp+10h] BYREF
  int *v22; // [rsp+90h] [rbp+18h]
  unsigned __int8 **v23; // [rsp+98h] [rbp+20h]

  v23 = a4;
  v22 = a3;
  *a2 = 4;
  *a4 = 0;
  *a3 = 0;
  v18 = (char *)this + 248;
  if ( (unsigned int)CSharedLock::Lock((CRemoteHiPerfEnum *)((char *)this + 264), 0x2710u) )
  {
    TransferArrayBlob = 0;
    v6 = 0;
    v7 = 0;
    if ( CFlexArray::Size((CRemoteHiPerfEnum *)((char *)this + 24)) > 0 )
    {
      v8 = 0;
      v9 = 0;
      if ( CFlexArray::Size((CRemoteHiPerfEnum *)((char *)this + 24)) )
      {
        do
        {
          v10 = (CWbemInstance ***)CFlexArray::operator[]((char *)this + 24, v9);
          ActualTransferBlobSize = CWbemInstance::GetActualTransferBlobSize(**v10);
          if ( ActualTransferBlobSize != -8 )
          {
            v6 += ActualTransferBlobSize + 8;
            ++v8;
          }
          ++v9;
        }
        while ( v9 < CFlexArray::Size((CRemoteHiPerfEnum *)((char *)this + 24)) );
        if ( v6 > 0 )
        {
          v12 = v6;
          v6 += 8;
          v13 = (unsigned __int8 *)CoTaskMemAlloc(v6);
          v7 = v13;
          if ( v13 )
          {
            *(_DWORD *)v13 = 1;
            *((_DWORD *)v13 + 1) = v8;
            v21 = v13 + 8;
            v14 = 0;
            while ( v14 < CFlexArray::Size((CRemoteHiPerfEnum *)((char *)this + 24)) )
            {
              v15 = **(CWbemInstance ***)CFlexArray::operator[]((char *)this + 24, v14);
              if ( (int)(CWbemInstance::GetActualTransferBlobSize(v15) + 8) <= 0
                || (v20 = 0,
                    TransferArrayBlob = CWbemInstance::GetTransferArrayBlob(v15, v12, &v21, &v20),
                    TransferArrayBlob < 0) )
              {
                ++v14;
                if ( TransferArrayBlob < 0 )
                {
                  CoTaskMemFree(v7);
                  v7 = 0;
                  v6 = 0;
                  goto LABEL_19;
                }
              }
              else
              {
                v12 -= v20;
                ++v14;
              }
            }
            CGarbageCollectArray::GarbageCollect((CRemoteHiPerfEnum *)((char *)this + 128), -1);
          }
          else
          {
            TransferArrayBlob = -2147217402;
          }
        }
      }
    }
LABEL_19:
    *v23 = v7;
    *v22 = v6;
    if ( TransferArrayBlob < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, TransferArrayBlob);
    }
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_03c64eaa4d8c32ecfb51fbe2c30fec97_Traceguids,
        (unsigned int)TransferArrayBlob);
    }
  }
  else
  {
    TransferArrayBlob = 262148;
  }
  CHiPerfLockAccess::~CHiPerfLockAccess((CHiPerfLockAccess *)&v18);
  return (unsigned int)TransferArrayBlob;
}

```

## disassembly

```asm
0x18008ba58  mov     rax, rsp
0x18008ba5b  mov     [rax+20h], r9
0x18008ba5f  mov     [rax+18h], r8
0x18008ba63  push    rbx
0x18008ba64  push    rbp
0x18008ba65  push    rsi
0x18008ba66  push    rdi
0x18008ba67  push    r12
0x18008ba69  push    r13
0x18008ba6b  push    r14
0x18008ba6d  push    r15
0x18008ba6f  sub     rsp, 38h
0x18008ba73  mov     r13, rcx
0x18008ba76  mov     dword ptr [rdx], 4
0x18008ba7c  mov     qword ptr [r9], 0
0x18008ba83  mov     dword ptr [r8], 0
0x18008ba8a  add     rcx, 0F8h
0x18008ba91  mov     [rax-58h], rcx
0x18008ba95  mov     dword ptr [rax-50h], 0
0x18008ba9c  add     rcx, 10h; this
0x18008baa0  mov     edx, 2710h; unsigned int
0x18008baa5  call    ?Lock@CSharedLock@@QEAAHK@Z; CSharedLock::Lock(ulong)
0x18008baaa  mov     [rsp+78h+var_50], eax
0x18008baae  test    eax, eax
0x18008bab0  jnz     short loc_18008BABC
0x18008bab2  mov     ebx, 40004h
0x18008bab7  jmp     loc_18008BC4E
0x18008babc  xor     ebx, ebx
0x18008babe  xor     edi, edi
0x18008bac0  xor     esi, esi
0x18008bac2  lea     r14, [r13+18h]
0x18008bac6  mov     rcx, r14
0x18008bac9  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18008bacf  test    eax, eax
0x18008bad1  jle     loc_18008BBEC
0x18008bad7  xor     r12d, r12d
0x18008bada  xor     ebp, ebp
0x18008badc  mov     rcx, r14
0x18008badf  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18008bae5  test    eax, eax
0x18008bae7  jz      loc_18008BBEC
0x18008baed  mov     edx, ebp
0x18008baef  mov     rcx, r14
0x18008baf2  call    cs:__imp_??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x18008baf8  mov     rcx, [rax]
0x18008bafb  mov     rcx, [rcx]; this
0x18008bafe  call    ?GetActualTransferBlobSize@CWbemInstance@@QEAAJXZ; CWbemInstance::GetActualTransferBlobSize(void)
0x18008bb03  lea     ecx, [rax+8]
0x18008bb06  test    ecx, ecx
0x18008bb08  jz      short loc_18008BB12
0x18008bb0a  add     edi, 8
0x18008bb0d  add     edi, eax
0x18008bb0f  inc     r12d
0x18008bb12  inc     ebp
0x18008bb14  mov     rcx, r14
0x18008bb17  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18008bb1d  cmp     ebp, eax
0x18008bb1f  jb      short loc_18008BAED
0x18008bb21  test    edi, edi
0x18008bb23  jle     loc_18008BBEC
0x18008bb29  mov     r15d, edi
0x18008bb2c  add     edi, 8
0x18008bb2f  movsxd  rcx, edi; cb
0x18008bb32  call    cs:__imp_CoTaskMemAlloc
0x18008bb38  mov     rsi, rax
0x18008bb3b  test    rax, rax
0x18008bb3e  jz      loc_18008BBE7
0x18008bb44  mov     dword ptr [rax], 1
0x18008bb4a  mov     [rax+4], r12d
0x18008bb4e  lea     rcx, [rax+8]
0x18008bb52  mov     [rsp+78h+arg_8], rcx
0x18008bb5a  xor     ebp, ebp
0x18008bb5c  mov     rcx, r14
0x18008bb5f  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18008bb65  cmp     ebp, eax
0x18008bb67  jnb     short loc_18008BBD6
0x18008bb69  mov     edx, ebp
0x18008bb6b  mov     rcx, r14
0x18008bb6e  call    cs:__imp_??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x18008bb74  mov     rcx, [rax]
0x18008bb77  mov     r12, [rcx]
0x18008bb7a  mov     rcx, r12; this
0x18008bb7d  call    ?GetActualTransferBlobSize@CWbemInstance@@QEAAJXZ; CWbemInstance::GetActualTransferBlobSize(void)
0x18008bb82  add     eax, 8
0x18008bb85  test    eax, eax
0x18008bb87  jle     short loc_18008BBC1
0x18008bb89  mov     [rsp+78h+arg_0], 0
0x18008bb94  lea     r9, [rsp+78h+arg_0]; int *
0x18008bb9c  lea     r8, [rsp+78h+arg_8]; unsigned __int8 **
0x18008bba4  mov     edx, r15d; int
0x18008bba7  mov     rcx, r12; this
0x18008bbaa  call    ?GetTransferArrayBlob@CWbemInstance@@QEAAJJPEAPEAEPEAJ@Z; CWbemInstance::GetTransferArrayBlob(long,uchar * *,long *)
0x18008bbaf  mov     ebx, eax
0x18008bbb1  test    eax, eax
0x18008bbb3  js      short loc_18008BBC1
0x18008bbb5  sub     r15d, [rsp+78h+arg_0]
0x18008bbbd  inc     ebp
0x18008bbbf  jmp     short loc_18008BB5C
0x18008bbc1  inc     ebp
0x18008bbc3  test    ebx, ebx
0x18008bbc5  jns     short loc_18008BB5C
0x18008bbc7  mov     rcx, rsi; pv
0x18008bbca  call    cs:__imp_CoTaskMemFree
0x18008bbd0  xor     esi, esi
0x18008bbd2  xor     edi, edi
0x18008bbd4  jmp     short loc_18008BBEC
0x18008bbd6  lea     rcx, [r13+80h]; this
0x18008bbdd  or      edx, 0FFFFFFFFh; int
0x18008bbe0  call    ?GarbageCollect@CGarbageCollectArray@@QEAAHH@Z; CGarbageCollectArray::GarbageCollect(int)
0x18008bbe5  jmp     short loc_18008BBEC
0x18008bbe7  mov     ebx, 80041006h
0x18008bbec  mov     rax, [rsp+78h+arg_18]
0x18008bbf4  mov     [rax], rsi
0x18008bbf7  mov     rax, [rsp+78h+arg_10]
0x18008bbff  mov     [rax], edi
0x18008bc01  test    ebx, ebx
0x18008bc03  jns     short loc_18008BC16
0x18008bc05  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008bc0b  mov     edx, ebx
0x18008bc0d  mov     rcx, rax
0x18008bc10  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008bc16  lea     rax, WPP_GLOBAL_Control
0x18008bc1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bc24  cmp     rcx, rax
0x18008bc27  jz      short loc_18008BC4E
0x18008bc29  test    byte ptr [rcx+1Ch], 1
0x18008bc2d  jz      short loc_18008BC4E
0x18008bc2f  cmp     byte ptr [rcx+19h], 2
0x18008bc33  jb      short loc_18008BC4E
0x18008bc35  mov     edx, 11h
0x18008bc3a  mov     r9d, ebx
0x18008bc3d  lea     r8, WPP_03c64eaa4d8c32ecfb51fbe2c30fec97_Traceguids
0x18008bc44  mov     rcx, [rcx+10h]
0x18008bc48  call    WPP_SF_d
0x18008bc4d  nop
0x18008bc4e  lea     rcx, [rsp+78h+var_58]; this
0x18008bc53  call    ??1CHiPerfLockAccess@@QEAA@XZ; CHiPerfLockAccess::~CHiPerfLockAccess(void)
0x18008bc58  mov     eax, ebx
0x18008bc5a  add     rsp, 38h
0x18008bc5e  pop     r15
0x18008bc60  pop     r14
0x18008bc62  pop     r13
0x18008bc64  pop     r12
0x18008bc66  pop     rdi
0x18008bc67  pop     rsi
0x18008bc68  pop     rbp
0x18008bc69  pop     rbx
0x18008bc6a  retn
```
