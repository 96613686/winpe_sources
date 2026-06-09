# CKsProxy::QueryInternalConnections(ulong,_PinDirection,IPin * *,ulong *)

- ea: `0x18000c1f4`
- end: `0x18000c6e7`
- name: `?QueryInternalConnections@CKsProxy@@QEAAJKW4_PinDirection@@PEAPEAUIPin@@PEAK@Z`
- size: `1267`
- prototype: `__int64 __fastcall(CKsProxy *this, unsigned int, enum _PinDirection, struct IPin **, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18000a700`
- `0x18002c170`

## callees

- `0x18000c1f4`
- `0x18000c6f0`
- `0x18000c93c`
- `0x180015f70`
- `0x180016114`
- `0x18001f1c4`
- `0x18001f210`
- `0x18001ffb0`
- `0x180045010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c2f1`
- `KERNEL32!GetLastError` at `0x18000c5df`
- `KERNEL32!GetLastError` at `0x18000c62e`
- `KERNEL32!GetLastError` at `0x18000c2f1`
- `KERNEL32!GetLastError` at `0x18000c5df`
- `KERNEL32!GetLastError` at `0x18000c62e`
- `KERNEL32!CreateEventW` at `0x18000c28f`
- `KERNEL32!CreateEventW` at `0x18000c28f`
- `KERNEL32!CloseHandle` at `0x18000c320`
- `KERNEL32!CloseHandle` at `0x18000c320`
- `KERNEL32!GetOverlappedResult` at `0x18000c617`
- `KERNEL32!GetOverlappedResult` at `0x18000c617`
- `KERNEL32!DeviceIoControl` at `0x18000c2dd`
- `KERNEL32!DeviceIoControl` at `0x18000c2dd`

## pseudocode

```c
__int64 __fastcall CKsProxy::QueryInternalConnections(
        CKsProxy *this,
        unsigned int a2,
        enum _PinDirection a3,
        struct IPin **a4,
        unsigned int *a5)
{
  unsigned int *v5; // r14
  enum _PinDirection v6; // edi
  unsigned int v7; // r15d
  char *m_FilterHandle; // rsi
  signed int LastError; // eax
  signed int v11; // ebx
  void *v12; // r12
  unsigned int v13; // ebx
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rdx
  struct KSMULTIPLE_ITEM *v16; // r13
  unsigned int Count; // ecx
  struct KSTOPOLOGY_CONNECTION *v18; // r11
  CKsProxy *v19; // rcx
  unsigned int v20; // edi
  __int64 v21; // rbx
  CBaseList::CNode *m_pFirst; // r15
  char *m_pObject; // rsi
  __int64 v24; // rax
  int v25; // esi
  unsigned int v26; // eax
  unsigned int j; // r10d
  struct KSTOPOLOGY_CONNECTION *v29; // r9
  __int64 v30; // rdi
  CKsProxy *v31; // r13
  CBaseList::CNode *v32; // rsi
  struct CBasePin *v33; // r15
  signed int v34; // eax
  signed int v35; // eax
  unsigned int i; // r10d
  struct KSTOPOLOGY_CONNECTION *v37; // r9
  unsigned int OutBuffer; // [rsp+48h] [rbp-51h] BYREF
  DWORD BytesReturned; // [rsp+4Ch] [rbp-4Dh] BYREF
  __int64 v40; // [rsp+50h] [rbp-49h] BYREF
  struct KSMULTIPLE_ITEM *v41; // [rsp+58h] [rbp-41h] BYREF
  int (__fastcall ***v42)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-39h]
  struct _OVERLAPPED Overlapped; // [rsp+70h] [rbp-29h] BYREF
  GUID InBuffer; // [rsp+90h] [rbp-9h] BYREF
  int v45; // [rsp+A0h] [rbp+7h]
  int v46; // [rsp+A4h] [rbp+Bh]

  v5 = a5;
  OutBuffer = 0;
  v41 = 0;
  v6 = a3;
  v7 = a2;
  if ( !a5 || *a5 && !a4 )
    return 2147500035LL;
  m_FilterHandle = (char *)this->m_FilterHandle;
  BytesReturned = 0;
  v45 = 1;
  v46 = 1;
  InBuffer = GUID_8c134960_51ad_11cf_878a_94f801c10000;
  if ( (unsigned __int64)(m_FilterHandle - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    memset(&Overlapped, 0, 24);
    Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
    if ( Overlapped.hEvent )
    {
      if ( DeviceIoControl(m_FilterHandle, 0x2F0003u, &InBuffer, 0x18u, &OutBuffer, 4u, &BytesReturned, &Overlapped) )
      {
        if ( Overlapped.Internal == 257 )
        {
          v11 = -2147024875;
        }
        else if ( Overlapped.Internal == 261 )
        {
          v11 = -2147024662;
        }
        else
        {
          v11 = Overlapped.Internal == 263 ? -2147023595 : 0;
        }
      }
      else
      {
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        if ( v11 == -2147023899 )
        {
          if ( GetOverlappedResult(m_FilterHandle, &Overlapped, &BytesReturned, 1) )
          {
            v11 = 0;
          }
          else
          {
            v35 = GetLastError();
            v11 = v35;
            if ( v35 > 0 )
              v11 = (unsigned __int16)v35 | 0x80070000;
          }
        }
        v6 = a3;
      }
      CloseHandle(Overlapped.hEvent);
    }
    else
    {
      v34 = GetLastError();
      v11 = v34;
      if ( v34 > 0 )
      {
        v6 = a3;
        v11 = (unsigned __int16)v34 | 0x80070000;
      }
    }
    if ( v11 >= 0 )
    {
      if ( OutBuffer < 2 )
      {
        *a5 = 0;
        return 0;
      }
      v12 = operator new[](saturated_mul(OutBuffer, 4u));
      if ( v12 )
      {
        v13 = -2147467263;
        if ( (int)CKsProxy::QueryTopologyItems(this, 2, &v41) >= 0 )
        {
          memset_0(v12, 0, 4LL * OutBuffer);
          v16 = v41;
          Count = v41->Count;
          v18 = (struct KSTOPOLOGY_CONNECTION *)&v41[1];
          if ( v6 )
          {
            if ( Count )
            {
              for ( i = 0; i < Count; ++i )
              {
                v37 = &v18[i];
                if ( v37->ToNode == -1 && v37->ToNodePin == v7 )
                  FollowToTopology(v18, Count, v7, v37, (unsigned int *)v12);
                Count = v16->Count;
              }
            }
          }
          else if ( Count )
          {
            for ( j = 0; j < Count; ++j )
            {
              v29 = &v18[j];
              if ( v29->FromNode == -1 && v29->FromNodePin == v7 )
                FollowFromTopology(v18, Count, v7, v29, (unsigned int *)v12);
              Count = v16->Count;
            }
          }
          v19 = (CKsProxy *)OutBuffer;
          v20 = 0;
          v21 = 0;
          if ( OutBuffer )
          {
            while ( 1 )
            {
              if ( (_DWORD)v21 == v7 || !*((_DWORD *)v12 + v21) )
                goto LABEL_31;
              m_pFirst = this->m_PinList.m_pFirst;
              if ( !m_pFirst )
                goto LABEL_30;
              do
              {
                m_pObject = (char *)m_pFirst->m_pObject;
                m_pFirst = m_pFirst->m_pNext;
                BytesReturned = 0;
                if ( m_pObject )
                {
                  v24 = *((_QWORD *)m_pObject + 3);
                  v42 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))(m_pObject + 24);
                  (*(void (__fastcall **)(char *, DWORD *))(v24 + 72))(m_pObject + 24, &BytesReturned);
                  v15 = BytesReturned;
                  if ( !BytesReturned )
                  {
                    v25 = *((_DWORD *)m_pObject + 102);
                    goto LABEL_26;
                  }
                  if ( BytesReturned == 1 )
                  {
                    v40 = 0;
                    if ( (**v42)(v42, &GUID_48c5e0d4_99ee_454b_a672_8ac5fb5deaed, &v40) >= 0 )
                    {
                      v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 32LL))(v40);
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
                      goto LABEL_26;
                    }
                  }
                }
                v25 = -1;
LABEL_26:
                v26 = v20 + 1;
                if ( v25 != (_DWORD)v21 )
                  v26 = v20;
                v20 = v26;
              }
              while ( m_pFirst );
              v19 = (CKsProxy *)OutBuffer;
LABEL_30:
              v7 = a2;
LABEL_31:
              v21 = (unsigned int)(v21 + 1);
              if ( (unsigned int)v21 >= (unsigned int)v19 )
              {
                v5 = a5;
                break;
              }
            }
          }
          if ( *v5 && v20 <= *v5 )
          {
            v13 = 0;
            v30 = 0;
            *v5 = 0;
            if ( (_DWORD)v19 )
            {
              v31 = this;
              do
              {
                if ( (_DWORD)v30 != v7 )
                {
                  if ( *((_DWORD *)v12 + v30) )
                  {
                    v32 = v31->m_PinList.m_pFirst;
                    if ( v32 )
                    {
                      do
                      {
                        v33 = (struct CBasePin *)v32->m_pObject;
                        v32 = v32->m_pNext;
                        if ( CKsProxy::GetPinFactoryId(v19, v33) == (_DWORD)v30 )
                        {
                          a4[*v5] = (struct IPin *)((unsigned __int64)&v33->IPin & -(__int64)(v33 != 0));
                          v33->AddRef(&v33->IPin);
                          ++*v5;
                        }
                      }
                      while ( v32 );
                      v19 = (CKsProxy *)OutBuffer;
                      v7 = a2;
                      v31 = this;
                    }
                  }
                }
                v30 = (unsigned int)(v30 + 1);
              }
              while ( (unsigned int)v30 < (unsigned int)v19 );
              v16 = v41;
            }
          }
          else
          {
            *v5 = v20;
            v13 = v20 != 0;
          }
          operator delete(v16, v15);
        }
        operator delete(v12, v14);
        return v13;
      }
    }
  }
  return 2147500033LL;
}

```

## disassembly

```asm
0x18000c1f4  mov     rax, rsp
0x18000c1f7  mov     [rax+20h], r9
0x18000c1fb  mov     [rax+18h], r8d
0x18000c1ff  mov     [rax+10h], edx
0x18000c202  mov     [rax+8], rcx
0x18000c206  push    rbp
0x18000c207  push    rbx
0x18000c208  push    rsi
0x18000c209  push    rdi
0x18000c20a  push    r12
0x18000c20c  push    r13
0x18000c20e  push    r14
0x18000c210  push    r15
0x18000c212  lea     rbp, [rax-57h]
0x18000c216  sub     rsp, 0A8h
0x18000c21d  mov     r14, [rbp+4Fh+arg_20]
0x18000c221  xor     r12d, r12d
0x18000c224  mov     [rbp+4Fh+OutBuffer], r12d
0x18000c228  mov     rax, r9
0x18000c22b  mov     [rbp+4Fh+var_90], r12
0x18000c22f  mov     edi, r8d
0x18000c232  mov     r15d, edx
0x18000c235  mov     r13, rcx
0x18000c238  test    r14, r14
0x18000c23b  jz      loc_18000C657
0x18000c241  cmp     [r14], r12d
0x18000c244  jnz     loc_18000C64E
0x18000c24a  mov     rsi, [r13+170h]
0x18000c251  mov     ecx, 1
0x18000c256  movups  xmm0, xmmword ptr cs:_GUID_8c134960_51ad_11cf_878a_94f801c10000.Data1
0x18000c25d  mov     [rbp+4Fh+BytesReturned], r12d
0x18000c261  mov     [rbp+4Fh+var_48], ecx
0x18000c264  lea     rax, [rsi-1]
0x18000c268  mov     [rbp+4Fh+var_44], ecx
0x18000c26b  movdqu  [rbp+4Fh+InBuffer], xmm0
0x18000c270  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c274  ja      loc_18000C6DD
0x18000c27a  xorps   xmm0, xmm0
0x18000c27d  mov     edx, ecx; bManualReset
0x18000c27f  xor     ecx, ecx; lpEventAttributes
0x18000c281  xor     r9d, r9d; lpName
0x18000c284  xor     r8d, r8d; bInitialState
0x18000c287  movups  xmmword ptr [rbp+4Fh+Overlapped.Internal], xmm0
0x18000c28b  movups  xmmword ptr [rbp+4Fh+Overlapped.10h], xmm0
0x18000c28f  call    cs:__imp_CreateEventW
0x18000c296  nop     dword ptr [rax+rax+00h]
0x18000c29b  mov     [rbp+4Fh+Overlapped.hEvent], rax
0x18000c29f  test    rax, rax
0x18000c2a2  jz      loc_18000C5DF
0x18000c2a8  lea     rax, [rbp+4Fh+Overlapped]
0x18000c2ac  mov     r9d, 18h; nInBufferSize
0x18000c2b2  mov     [rsp+38h], rax; lpOverlapped
0x18000c2b7  lea     r8, [rbp+4Fh+InBuffer]; lpInBuffer
0x18000c2bb  lea     rax, [rbp+4Fh+BytesReturned]
0x18000c2bf  mov     edx, 2F0003h; dwIoControlCode
0x18000c2c4  mov     [rsp+0E0h+lpBytesReturned], rax; lpBytesReturned
0x18000c2c9  mov     rcx, rsi; hDevice
0x18000c2cc  lea     rax, [rbp+4Fh+OutBuffer]
0x18000c2d0  mov     [rsp+0E0h+nOutBufferSize], 4; nOutBufferSize
0x18000c2d8  mov     [rsp+0E0h+lpOutBuffer], rax; lpOutBuffer
0x18000c2dd  call    cs:__imp_DeviceIoControl
0x18000c2e4  nop     dword ptr [rax+rax+00h]
0x18000c2e9  test    eax, eax
0x18000c2eb  jnz     loc_18000C4E6
0x18000c2f1  call    cs:__imp_GetLastError
0x18000c2f8  nop     dword ptr [rax+rax+00h]
0x18000c2fd  mov     ebx, eax
0x18000c2ff  mov     edi, 80070000h
0x18000c304  test    eax, eax
0x18000c306  jle     short loc_18000C30D
0x18000c308  movzx   ebx, ax
0x18000c30b  or      ebx, edi
0x18000c30d  cmp     ebx, 800703E5h
0x18000c313  jz      loc_18000C606
0x18000c319  mov     edi, [rbp+4Fh+arg_10]
0x18000c31c  mov     rcx, [rbp+4Fh+Overlapped.hEvent]; hObject
0x18000c320  call    cs:__imp_CloseHandle
0x18000c327  nop     dword ptr [rax+rax+00h]
0x18000c32c  test    ebx, ebx
0x18000c32e  js      loc_18000C6DD
0x18000c334  cmp     [rbp+4Fh+OutBuffer], 2
0x18000c338  jb      loc_18000C67F
0x18000c33e  mov     ecx, [rbp+4Fh+OutBuffer]
0x18000c341  mov     eax, 4
0x18000c346  mul     rcx
0x18000c349  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c350  cmovb   rax, rcx
0x18000c354  mov     rcx, rax; unsigned __int64
0x18000c357  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000c35c  mov     r12, rax
0x18000c35f  test    rax, rax
0x18000c362  jz      loc_18000C6DD
0x18000c368  lea     r8, [rbp+4Fh+var_90]; struct KSMULTIPLE_ITEM **
0x18000c36c  mov     edx, 2; unsigned int
0x18000c371  mov     rcx, r13; this
0x18000c374  mov     ebx, 80004001h
0x18000c379  call    ?QueryTopologyItems@CKsProxy@@QEAAJKPEAPEAUKSMULTIPLE_ITEM@@@Z; CKsProxy::QueryTopologyItems(ulong,KSMULTIPLE_ITEM * *)
0x18000c37e  test    eax, eax
0x18000c380  js      loc_18000C4BF
0x18000c386  mov     r8d, [rbp+4Fh+OutBuffer]
0x18000c38a  xor     edx, edx; Val
0x18000c38c  shl     r8, 2; Size
0x18000c390  mov     rcx, r12; void *
0x18000c393  call    memset_0
0x18000c398  mov     r13, [rbp+4Fh+var_90]
0x18000c39c  mov     ecx, [r13+4]
0x18000c3a0  lea     r11, [r13+8]
0x18000c3a4  test    edi, edi
0x18000c3a6  jz      loc_18000C511
0x18000c3ac  test    ecx, ecx
0x18000c3ae  jnz     loc_18000C6A0
0x18000c3b4  mov     ecx, [rbp+4Fh+OutBuffer]
0x18000c3b7  xor     edi, edi
0x18000c3b9  xor     ebx, ebx
0x18000c3bb  test    ecx, ecx
0x18000c3bd  jz      loc_18000C4A3
0x18000c3c3  mov     r14, [rbp+4Fh+arg_0]
0x18000c3c7  cmp     ebx, r15d
0x18000c3ca  jz      loc_18000C495
0x18000c3d0  cmp     dword ptr [r12+rbx*4], 0
0x18000c3d5  jz      loc_18000C495
0x18000c3db  mov     r15, [r14+120h]
0x18000c3e2  test    r15, r15
0x18000c3e5  jz      loc_18000C491
0x18000c3eb  mov     rsi, [r15+10h]
0x18000c3ef  mov     r15, [r15+8]
0x18000c3f3  mov     [rbp+4Fh+BytesReturned], 0
0x18000c3fa  test    rsi, rsi
0x18000c3fd  jz      loc_18000C5D7
0x18000c403  lea     rcx, [rsi+18h]
0x18000c407  mov     rax, [rcx]
0x18000c40a  lea     rdx, [rbp+4Fh+BytesReturned]
0x18000c40e  mov     [rbp+4Fh+var_88], rcx
0x18000c412  mov     rax, [rax+48h]
0x18000c416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c41b  mov     edx, [rbp+4Fh+BytesReturned]
0x18000c41e  test    edx, edx
0x18000c420  jz      loc_18000C4DE
0x18000c426  cmp     edx, 1
0x18000c429  jnz     loc_18000C5D7
0x18000c42f  mov     rcx, [rbp+4Fh+var_88]
0x18000c433  lea     r8, [rbp+4Fh+var_98]
0x18000c437  lea     rdx, _GUID_48c5e0d4_99ee_454b_a672_8ac5fb5deaed
0x18000c43e  mov     [rbp+4Fh+var_98], 0
0x18000c446  mov     rax, [rcx]
0x18000c449  mov     rax, [rax]
0x18000c44c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c451  test    eax, eax
0x18000c453  js      loc_18000C5D7
0x18000c459  mov     rcx, [rbp+4Fh+var_98]
0x18000c45d  mov     rax, [rcx]
0x18000c460  mov     rax, [rax+20h]
0x18000c464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c469  mov     rcx, [rbp+4Fh+var_98]
0x18000c46d  mov     esi, eax
0x18000c46f  mov     rdx, [rcx]
0x18000c472  mov     rax, [rdx+10h]
0x18000c476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c47b  cmp     esi, ebx
0x18000c47d  lea     eax, [rdi+1]
0x18000c480  cmovnz  eax, edi
0x18000c483  mov     edi, eax
0x18000c485  test    r15, r15
0x18000c488  jnz     loc_18000C3EB
0x18000c48e  mov     ecx, [rbp+4Fh+OutBuffer]; this
0x18000c491  mov     r15d, [rbp+4Fh+arg_8]
0x18000c495  inc     ebx
0x18000c497  cmp     ebx, ecx
0x18000c499  jb      loc_18000C3C7
0x18000c49f  mov     r14, [rbp+4Fh+arg_20]
0x18000c4a3  cmp     dword ptr [r14], 0
0x18000c4a7  jnz     loc_18000C547
0x18000c4ad  xor     ebx, ebx
0x18000c4af  mov     [r14], edi
0x18000c4b2  test    edi, edi
0x18000c4b4  setnz   bl
0x18000c4b7  mov     rcx, r13; void *
0x18000c4ba  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c4bf  mov     rcx, r12; void *
0x18000c4c2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c4c7  mov     eax, ebx
0x18000c4c9  add     rsp, 0A8h
0x18000c4d0  pop     r15
0x18000c4d2  pop     r14
0x18000c4d4  pop     r13
0x18000c4d6  pop     r12
0x18000c4d8  pop     rdi
0x18000c4d9  pop     rsi
0x18000c4da  pop     rbx
0x18000c4db  pop     rbp
0x18000c4dc  retn
0x18000c4de  mov     esi, [rsi+198h]
0x18000c4e4  jmp     short loc_18000C47B
0x18000c4e6  mov     rax, [rbp+4Fh+Overlapped.Internal]
0x18000c4ea  sub     rax, 101h
0x18000c4f0  jz      loc_18000C675
0x18000c4f6  sub     rax, 4
0x18000c4fa  jz      loc_18000C66B
0x18000c500  cmp     rax, 2
0x18000c504  jz      loc_18000C661
0x18000c50a  xor     ebx, ebx
0x18000c50c  jmp     loc_18000C31C
0x18000c511  test    ecx, ecx
0x18000c513  jz      loc_18000C3B4
0x18000c519  xor     r10d, r10d
0x18000c51c  mov     r9d, r10d
0x18000c51f  shl     r9, 4
0x18000c523  add     r9, r11; struct KSTOPOLOGY_CONNECTION *
0x18000c526  cmp     dword ptr [r9], 0FFFFFFFFh
0x18000c52a  jnz     short loc_18000C536
0x18000c52c  cmp     [r9+4], r15d
0x18000c530  jz      loc_18000C689
0x18000c536  mov     ecx, [r13+4]
0x18000c53a  inc     r10d
0x18000c53d  cmp     r10d, ecx
0x18000c540  jb      short loc_18000C51C
0x18000c542  jmp     loc_18000C3B4
0x18000c547  cmp     edi, [r14]
0x18000c54a  ja      loc_18000C4AD
0x18000c550  xor     ebx, ebx
0x18000c552  xor     edi, edi
0x18000c554  mov     [r14], ebx
0x18000c557  test    ecx, ecx
0x18000c559  jz      loc_18000C4B7
0x18000c55f  mov     r13, [rbp+4Fh+arg_0]
0x18000c563  cmp     edi, r15d
0x18000c566  jz      short loc_18000C5A2
0x18000c568  cmp     [r12+rdi*4], ebx
0x18000c56c  jz      short loc_18000C5A2
0x18000c56e  mov     rsi, [r13+120h]
0x18000c575  test    rsi, rsi
0x18000c578  jz      short loc_18000C5A2
0x18000c57a  mov     r13, [rbp+4Fh+arg_18]
0x18000c57e  mov     r15, [rsi+10h]
0x18000c582  mov     rsi, [rsi+8]
0x18000c586  mov     rdx, r15; struct CBasePin *
0x18000c589  call    ?GetPinFactoryId@CKsProxy@@QEAAKPEAVCBasePin@@@Z; CKsProxy::GetPinFactoryId(CBasePin *)
0x18000c58e  cmp     eax, edi
0x18000c590  jz      short loc_18000C5B1
0x18000c592  test    rsi, rsi
0x18000c595  jnz     short loc_18000C57E
0x18000c597  mov     ecx, [rbp+4Fh+OutBuffer]
0x18000c59a  mov     r15d, [rbp+4Fh+arg_8]
0x18000c59e  mov     r13, [rbp+4Fh+arg_0]
0x18000c5a2  inc     edi
0x18000c5a4  cmp     edi, ecx
0x18000c5a6  jb      short loc_18000C563
0x18000c5a8  mov     r13, [rbp+4Fh+var_90]
0x18000c5ac  jmp     loc_18000C4B7
0x18000c5b1  mov     eax, [r14]
0x18000c5b4  lea     rcx, [r15+18h]
0x18000c5b8  neg     r15
0x18000c5bb  sbb     rdx, rdx
0x18000c5be  and     rdx, rcx
0x18000c5c1  mov     [r13+rax*8+0], rdx
0x18000c5c6  mov     rax, [rcx]
0x18000c5c9  mov     rax, [rax+8]
0x18000c5cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5d2  inc     dword ptr [r14]
0x18000c5d5  jmp     short loc_18000C592
0x18000c5d7  or      esi, 0FFFFFFFFh
0x18000c5da  jmp     loc_18000C47B
0x18000c5df  call    cs:__imp_GetLastError
0x18000c5e6  nop     dword ptr [rax+rax+00h]
0x18000c5eb  mov     ebx, eax
0x18000c5ed  test    eax, eax
0x18000c5ef  jle     loc_18000C32C
0x18000c5f5  mov     edi, [rbp+4Fh+arg_10]
0x18000c5f8  movzx   ebx, ax
0x18000c5fb  or      ebx, 80070000h
0x18000c601  jmp     loc_18000C32C
0x18000c606  mov     r9d, 1; bWait
0x18000c60c  lea     r8, [rbp+4Fh+BytesReturned]; lpNumberOfBytesTransferred
0x18000c610  lea     rdx, [rbp+4Fh+Overlapped]; lpOverlapped
0x18000c614  mov     rcx, rsi; hFile
0x18000c617  call    cs:__imp_GetOverlappedResult
0x18000c61e  nop     dword ptr [rax+rax+00h]
0x18000c623  test    eax, eax
0x18000c625  jz      short loc_18000C62E
0x18000c627  xor     ebx, ebx
0x18000c629  jmp     loc_18000C319
0x18000c62e  call    cs:__imp_GetLastError
0x18000c635  nop     dword ptr [rax+rax+00h]
0x18000c63a  mov     ebx, eax
0x18000c63c  test    eax, eax
0x18000c63e  jle     loc_18000C319
0x18000c644  movzx   ebx, ax
0x18000c647  or      ebx, edi
0x18000c649  jmp     loc_18000C319
0x18000c64e  test    rax, rax
0x18000c651  jnz     loc_18000C24A
0x18000c657  mov     eax, 80004003h
0x18000c65c  jmp     loc_18000C4C9
0x18000c661  mov     ebx, 80070515h
0x18000c666  jmp     loc_18000C31C
0x18000c66b  mov     ebx, 800700EAh
0x18000c670  jmp     loc_18000C31C
0x18000c675  mov     ebx, 80070015h
0x18000c67a  jmp     loc_18000C31C
0x18000c67f  mov     [r14], r12d
  ... truncated ...
```
