# MRxDAVFormatUserModeFsCtlRequest

- ea: `0x140010620`
- end: `0x14001143a`
- name: `MRxDAVFormatUserModeFsCtlRequest`
- size: `3610`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x1400018d4`
- `0x1400019bc`
- `0x140001a4c`
- `0x140001b64`
- `0x140001bc4`
- `0x140006900`
- `0x140006c00`
- `0x140010620`
- `0x14002609c`
- `0x140027bac`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1400106a9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400106e5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001076a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400107c5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010819`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400108ac`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001091f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400109d8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010a54`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010ab6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010b09`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010b53`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010c0d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010cd9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010d44`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010dbd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010e63`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010f75`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011088`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001112e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011242`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400112a5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011349`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001137d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400113f5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400106a9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400106e5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001076a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400107c5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010819`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400108ac`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001091f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400109d8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010a54`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010ab6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010b09`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010b53`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010c0d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010cd9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010d44`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010dbd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010e63`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010f75`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011088`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001112e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011242`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400112a5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011349`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001137d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400113f5`
- `ntoskrnl!ExAllocatePool2` at `0x140010f33`
- `ntoskrnl!ExAllocatePool2` at `0x140010f33`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400113c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400113c9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140010fc9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140010fc9`
- `ntoskrnl!wcschr` at `0x14001097a`
- `ntoskrnl!wcschr` at `0x14001097a`
- `ntoskrnl!IoCreateFileEx` at `0x14001104e`
- `ntoskrnl!IoCreateFileEx` at `0x14001104e`
- `ntoskrnl!NtClose` at `0x1400113af`
- `ntoskrnl!NtClose` at `0x1400113af`

## pseudocode

```c
__int64 __fastcall MRxDAVFormatUserModeFsCtlRequest(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v3; // r12
  NTSTATUS v4; // esi
  __int64 v7; // r13
  __int64 v8; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v10; // rbx
  HANDLE v11; // rax
  _QWORD *v12; // rcx
  __int64 v13; // rsi
  __int16 *v14; // rdi
  __int16 v15; // bx
  unsigned int v16; // eax
  __int16 *v17; // rdi
  __int64 v18; // rsi
  __int16 v19; // bx
  unsigned int v20; // eax
  __int16 *v21; // rdi
  __int64 v22; // rsi
  __int16 v23; // bx
  unsigned int v24; // eax
  _DWORD *v25; // rax
  __int64 v26; // rbx
  ULONG_PTR v27; // rsi
  PVOID v28; // rax
  __int64 v29; // rdi
  __int64 v30; // rbx
  HANDLE v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rbx
  unsigned int v34; // eax
  unsigned __int16 *v35; // r8
  unsigned int v36; // esi
  ULONG_PTR v37; // rbx
  char *v38; // rax
  char *v39; // rdi
  __int64 v40; // rbx
  unsigned int v41; // eax
  struct _SECURITY_CLIENT_CONTEXT *v42; // rdi
  __int64 v43; // rbx
  HANDLE v44; // rax
  int v45; // ebx
  __int64 v46; // rdi
  HANDLE v47; // rax
  int v48; // ebx
  __int64 v49; // rdi
  HANDLE v50; // rax
  int v51; // ecx
  int v52; // ecx
  int v53; // ecx
  __int64 v54; // rbx
  HANDLE v55; // rax
  unsigned int v56; // eax
  PVOID SecondaryBuffer; // rax
  unsigned int v58; // eax
  PVOID v59; // rax
  __int64 v60; // rbx
  HANDLE v61; // rax
  __int64 v62; // rcx
  __int64 v63; // rax
  __int64 v64; // r12
  __int64 v65; // r13
  __int64 v66; // rbx
  __int64 v67; // rdi
  HANDLE v68; // rax
  __int64 v69; // rdi
  signed __int32 v70; // ebx
  _WORD *v71; // r8
  _WORD *v72; // rax
  __int64 v73; // rcx
  __int64 v74; // rdx
  _WORD *v75; // rcx
  __int64 v76; // r15
  __int64 v77; // rax
  size_t v78; // rsi
  wchar_t *Pool2; // rax
  __int64 v80; // r11
  PCWSTR v81; // r11
  __int64 v82; // rbx
  HANDLE v83; // rax
  __int64 v84; // rdx
  _QWORD *v85; // r8
  _QWORD *v86; // rcx
  _QWORD *v87; // rdx
  __int64 v88; // rax
  __int64 v89; // rbx
  HANDLE v90; // rax
  __int64 v91; // rcx
  __int64 v92; // rax
  ULONG_PTR v93; // rbx
  PVOID v94; // rax
  _WORD *v95; // rdx
  void *v96; // rbx
  __int64 v97; // rdi
  unsigned int v98; // eax
  unsigned int v99; // eax
  __int64 v100; // rbx
  HANDLE v101; // rax
  __int64 v102; // rbx
  HANDLE v103; // rax
  _QWORD *Src; // [rsp+80h] [rbp-51h]
  wchar_t *Srca; // [rsp+80h] [rbp-51h]
  wchar_t *pszDest; // [rsp+88h] [rbp-49h]
  _DWORD *v108; // [rsp+90h] [rbp-41h]
  __int64 v109; // [rsp+98h] [rbp-39h]
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-21h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp+Fh] BYREF
  PSECURITY_CLIENT_CONTEXT ClientContext; // [rsp+138h] [rbp+67h]
  void *FileHandle; // [rsp+140h] [rbp+6Fh] BYREF

  v3 = *(_QWORD **)(a2 + 72);
  v4 = 0;
  v7 = a1;
  if ( v3 )
    v109 = v3[6];
  else
    v109 = 0;
  FileHandle = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  IoStatusBlock = 0;
  pszDest = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v8, 27, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v11 = PsGetCurrentThreadId();
      WPP_SF_qqq(v10, 28, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v11, v7, a2);
    }
  }
  if ( *(_DWORD *)(v7 + 744) == 17 )
  {
    *(_DWORD *)(a3 + 48) = 14;
    if ( *(_DWORD *)(a2 + 540) != 67108992 )
      goto LABEL_50;
    v42 = 0;
    ClientContext = 0;
LABEL_52:
    v51 = *(_DWORD *)(a2 + 540);
    *(_DWORD *)(a3 + 664) = v51;
    *(_DWORD *)(a3 + 668) = *(unsigned __int8 *)(a2 + 576);
    v52 = v51 - 67108984;
    if ( !v52 )
    {
      *(_DWORD *)(a3 + 680) = *(_DWORD *)(a2 + 568);
      goto LABEL_63;
    }
    v53 = v52 - 7;
    if ( !v53 )
    {
      *(_DWORD *)(a3 + 680) = 584;
      goto LABEL_63;
    }
    if ( v53 != 1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      {
        v54 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v55 = PsGetCurrentThreadId();
        WPP_SF_qq(v54, 39, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v55, v42);
      }
LABEL_64:
      v56 = *(_DWORD *)(a3 + 684);
      if ( v56 )
      {
        SecondaryBuffer = UMRxAllocateSecondaryBuffer(v7, v56);
        *(_QWORD *)(a3 + 688) = SecondaryBuffer;
        if ( !SecondaryBuffer )
        {
          v4 = -1073741670;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
          {
            v30 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v31 = PsGetCurrentThreadId();
            v32 = 40;
            goto LABEL_26;
          }
          goto LABEL_149;
        }
      }
      else
      {
        *(_QWORD *)(a3 + 688) = 0;
      }
      v58 = *(_DWORD *)(a3 + 680);
      if ( v58 )
      {
        v59 = UMRxAllocateSecondaryBuffer(v7, v58);
        *(_QWORD *)(a3 + 672) = v59;
        if ( !v59 )
        {
          v4 = -1073741670;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
          {
            v30 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v31 = PsGetCurrentThreadId();
            v32 = 41;
            goto LABEL_26;
          }
          goto LABEL_149;
        }
        memset(v59, 0, *(unsigned int *)(a3 + 680));
      }
      else
      {
        *(_QWORD *)(a3 + 672) = 0;
      }
      switch ( *(_DWORD *)(a3 + 664) )
      {
        case 0x4000078:
          v99 = *(_DWORD *)(a3 + 680);
          if ( v99 )
            memmove(*(void **)(a3 + 672), *(const void **)(a2 + 552), v99);
          break;
        case 0x400007F:
          v64 = v3[4];
          v65 = 0;
          if ( v64 )
            v65 = *(_QWORD *)(v64 + 136);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
          {
            v66 = *(_QWORD *)(a2 + 64);
            v67 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v68 = PsGetCurrentThreadId();
            WPP_SF_qqqq(v67, 42, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v68, a1, a2, v66);
          }
          v69 = *(_QWORD *)(a3 + 672);
          v70 = _InterlockedCompareExchange((volatile signed __int32 *)(v65 + 16), 0, 0);
          v71 = (_WORD *)(v65 + 668);
          v72 = (_WORD *)(v69 + 64);
          v73 = 2147483646;
          v74 = 260;
          do
          {
            if ( !v73 )
              break;
            if ( !*v71 )
              break;
            *v72++ = *v71++;
            --v73;
            --v74;
          }
          while ( v74 );
          v75 = v72 - 1;
          if ( v74 )
            v75 = v72;
          *v75 = 0;
          if ( v70 )
          {
            _InterlockedExchange((volatile __int32 *)(v65 + 16), 0);
            *(_DWORD *)(v65 + 20) = 1;
          }
          v76 = -1;
          *(_DWORD *)(v69 + 16) = v70;
          v77 = -1;
          do
            ++v77;
          while ( *(_WORD *)(v65 + 2 * v77 + 668) );
          v78 = (unsigned int)(2 * v77 + 22);
          Pool2 = (wchar_t *)ExAllocatePool2(258, v78, 1850103364);
          pszDest = Pool2;
          if ( !Pool2 )
          {
            v4 = -1073741670;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
            {
              v30 = *((_QWORD *)WPP_GLOBAL_Control + 3);
              v31 = PsGetCurrentThreadId();
              v32 = 43;
              goto LABEL_26;
            }
            goto LABEL_149;
          }
          memset(Pool2, 0, v78);
          StringCbCopyW(pszDest, v78, L"\\GLOBAL??\\");
          StringCbCopyW((STRSAFE_LPWSTR)(v80 + 20), v78 - 20, (STRSAFE_LPCWSTR)(v65 + 668));
          RtlInitUnicodeString(&DestinationString, v81);
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = 64;
          ObjectAttributes.ObjectName = &DestinationString;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v4 = IoCreateFileEx(
                 &FileHandle,
                 0x100081u,
                 &ObjectAttributes,
                 &IoStatusBlock,
                 0,
                 0x80u,
                 7u,
                 1u,
                 0x60u,
                 0,
                 0,
                 CreateFileTypeNone,
                 0,
                 0x900u,
                 0);
          if ( v4 < 0 )
          {
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
            {
              goto LABEL_149;
            }
            v82 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v83 = PsGetCurrentThreadId();
            v84 = 44;
LABEL_110:
            WPP_SF_qD(v82, v84, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v83, v4);
            goto LABEL_149;
          }
          v85 = (_QWORD *)(v64 + 200);
          *(_QWORD *)(v69 + 8) = FileHandle;
          v86 = (_QWORD *)(v64 + 208);
          v87 = (_QWORD *)(v64 + 216);
          if ( v70 )
          {
            *(_BYTE *)(v69 + 20) = *v85 != 0;
            *(_BYTE *)(v69 + 21) = *v86 != 0;
            *(_BYTE *)(v69 + 22) = *v87 != 0;
            if ( !*(_DWORD *)(v65 + 28) )
            {
              v88 = MEMORY[0xFFFFF78000000014];
              *v86 = MEMORY[0xFFFFF78000000014];
              *v87 = v88;
            }
            if ( *(_DWORD *)(v64 + 232) == 128 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
              {
                v89 = *((_QWORD *)WPP_GLOBAL_Control + 3);
                v90 = PsGetCurrentThreadId();
                WPP_SF_q(v89, 45, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v90);
                v86 = (_QWORD *)(v64 + 208);
                v87 = (_QWORD *)(v64 + 216);
                v85 = (_QWORD *)(v64 + 200);
              }
              *(_DWORD *)(v64 + 232) = 32;
              *(_BYTE *)(v65 + 63) = 1;
            }
            if ( *(_DWORD *)(v64 + 232) || *(_BYTE *)(v65 + 63) )
              *(_BYTE *)(v69 + 23) = 1;
          }
          else
          {
            *(_BYTE *)(v69 + 20) = *(_BYTE *)(v65 + 60);
            *(_BYTE *)(v69 + 21) = *(_BYTE *)(v65 + 61);
            *(_BYTE *)(v69 + 22) = *(_BYTE *)(v65 + 62);
            *(_BYTE *)(v69 + 23) = *(_BYTE *)(v65 + 63);
          }
          *(_QWORD *)(v69 + 24) = *v85;
          *(_QWORD *)(v69 + 32) = *v86;
          *(_QWORD *)(v69 + 40) = *v87;
          *(_DWORD *)(v69 + 56) = *(_DWORD *)(v64 + 232);
          *(_DWORD *)(v69 + 60) = *(_DWORD *)(v64 + 32);
          v91 = *(_QWORD *)(v109 + 48);
          if ( v91 )
          {
            v92 = -1;
            do
              ++v92;
            while ( *(_WORD *)(v91 + 2 * v92) );
            v7 = a1;
            v93 = (unsigned int)(2 * v92 + 2);
            v94 = UMRxAllocateSecondaryBuffer(a1, v93);
            *(_QWORD *)v69 = v94;
            if ( !v94 )
            {
              v4 = -1073741670;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
              {
                v30 = *((_QWORD *)WPP_GLOBAL_Control + 3);
                v31 = PsGetCurrentThreadId();
                v32 = 46;
                goto LABEL_26;
              }
              goto LABEL_149;
            }
            memset(v94, 0, v93);
            v95 = *(_WORD **)(v109 + 48);
            do
              ++v76;
            while ( v95[v76] );
            memmove(*(void **)v69, v95, 2 * v76);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
            {
              v96 = *(void **)v69;
              v97 = *((_QWORD *)WPP_GLOBAL_Control + 3);
              v98 = (unsigned int)PsGetCurrentThreadId();
              WPP_SF_qS(v97, 47, (unsigned int)WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v98, (__int64)v96);
            }
          }
          else
          {
            v7 = a1;
          }
          v42 = ClientContext;
          break;
        case 0x4000080:
          v62 = *(_QWORD *)(a3 + 672);
          if ( *(_DWORD *)(v7 + 744) == 17 )
          {
            *(_DWORD *)(v62 + 4) = *(_DWORD *)(v7 + 100);
            *(_DWORD *)v62 = *(_DWORD *)(v7 + 96);
            *(_QWORD *)(v62 + 8) = *(_QWORD *)(v7 + 104);
            v63 = *(_QWORD *)(v7 + 112);
          }
          else
          {
            v63 = 0;
            *(_QWORD *)v62 = 0;
            *(_QWORD *)(v62 + 8) = 0;
          }
          *(_QWORD *)(v62 + 16) = v63;
          break;
        default:
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
          {
            v60 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v61 = PsGetCurrentThreadId();
            WPP_SF_qq(v60, 48, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v61, v42);
          }
          break;
      }
      if ( *(_DWORD *)(v7 + 744) == 17 )
        goto LABEL_151;
      if ( !v42 )
      {
        v4 = -1073741811;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        {
          v100 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v101 = PsGetCurrentThreadId();
          WPP_SF_q(v100, 50, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v101);
        }
        goto LABEL_149;
      }
      v4 = UMRxImpersonateClient(v42);
      if ( v4 >= 0 )
        goto LABEL_151;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        goto LABEL_149;
      v82 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v83 = PsGetCurrentThreadId();
      v84 = 49;
      goto LABEL_110;
    }
    if ( !*(_DWORD *)(a2 + 568) && *(_DWORD *)(a2 + 572) == 2052 )
    {
      *(_DWORD *)(a3 + 680) = 24;
LABEL_63:
      *(_DWORD *)(a3 + 684) = *(_DWORD *)(a2 + 572);
      goto LABEL_64;
    }
LABEL_50:
    v4 = -1073741811;
    goto LABEL_149;
  }
  *(_DWORD *)(a3 + 48) = 13;
  v12 = *(_QWORD **)(v3[4] + 120LL);
  Src = v12;
  ClientContext = *(PSECURITY_CLIENT_CONTEXT *)(v3[5] + 40LL);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v13 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v14 = *(__int16 **)(v12[4] + 64LL);
      v15 = *v14;
      v16 = (unsigned int)PsGetCurrentThreadId();
      WPP_SF_qZd(v13, 29, (unsigned int)WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v16, (__int64)v14, v15);
      v12 = Src;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      {
        v17 = (__int16 *)v12[11];
        v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v19 = *v17;
        v20 = (unsigned int)PsGetCurrentThreadId();
        WPP_SF_qZd(v18, 30, (unsigned int)WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v20, (__int64)v17, v19);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      {
        v21 = (__int16 *)v3[10];
        v22 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v23 = *v21;
        v24 = (unsigned int)PsGetCurrentThreadId();
        WPP_SF_qZd(v22, 31, (unsigned int)WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v24, (__int64)v21, v23);
      }
    }
  }
  v25 = 0;
  v26 = *(_QWORD *)(*(_QWORD *)(v3[5] + 32LL) + 32LL);
  if ( v26 )
    v25 = *(_DWORD **)(v26 + 32);
  v108 = v25;
  v27 = **(unsigned __int16 **)(v26 + 64) + 2LL;
  v28 = UMRxAllocateSecondaryBuffer(v7, v27);
  v29 = (__int64)v28;
  if ( !v28 )
  {
    v4 = -1073741670;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v30 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v31 = PsGetCurrentThreadId();
      v32 = 32;
LABEL_26:
      WPP_SF_qD(v30, v32, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v31, -1073741670);
      goto LABEL_149;
    }
    goto LABEL_149;
  }
  memmove(v28, *(const void **)(*(_QWORD *)(v26 + 64) + 8LL), **(unsigned __int16 **)(v26 + 64));
  *(_WORD *)(v29 + 2 * (v27 >> 1) - 2) = 0;
  *(_QWORD *)(a3 + 640) = v29;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v33 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v34 = (unsigned int)PsGetCurrentThreadId();
    WPP_SF_qS(v33, 33, (unsigned int)WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v34, v29);
  }
  *(_DWORD *)(a3 + 648) = *v108;
  v35 = (unsigned __int16 *)Src[11];
  v36 = *v35 - **(unsigned __int16 **)(Src[4] + 64LL);
  Srca = wcschr((const wchar_t *)(*((_QWORD *)v35 + 1) + 2LL), 0x5Cu);
  v37 = v36 + *(unsigned __int16 *)v3[10] + 2;
  v38 = (char *)UMRxAllocateSecondaryBuffer(v7, v37);
  v39 = v38;
  if ( v38 )
  {
    memset(v38, 0, v37);
    memmove(v39, Srca, v36);
    memmove(&v39[2 * ((unsigned __int64)v36 >> 1)], *(const void **)(v3[10] + 8LL), *(unsigned __int16 *)v3[10]);
    v4 = 0;
    *(_WORD *)&v39[2 * (v37 >> 1) - 2] = 0;
    *(_QWORD *)(a3 + 656) = v39;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v40 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v41 = (unsigned int)PsGetCurrentThreadId();
      WPP_SF_qS(v40, 35, (unsigned int)WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v41, (__int64)v39);
    }
    v42 = ClientContext;
    *(_DWORD *)(a3 + 632) = *(_DWORD *)&ClientContext[1].SecurityQos.ContextTrackingMode;
    *(_DWORD *)(a3 + 636) = *((_DWORD *)&ClientContext[1].SecurityQos + 3);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      {
        v43 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v44 = PsGetCurrentThreadId();
        WPP_SF_qq(v43, 36, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v44, ClientContext);
      }
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v42 = ClientContext;
      }
      else
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
        {
          v45 = *(_DWORD *)&ClientContext[1].SecurityQos.ContextTrackingMode;
          v46 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v47 = PsGetCurrentThreadId();
          WPP_SF_qD(v46, 37, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v47, v45);
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
        {
          v48 = *((_DWORD *)&ClientContext[1].SecurityQos + 3);
          v49 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v50 = PsGetCurrentThreadId();
          WPP_SF_qD(v49, 38, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v50, v48);
        }
        v42 = ClientContext;
        v4 = 0;
      }
    }
    goto LABEL_52;
  }
  v4 = -1073741670;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v30 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v31 = PsGetCurrentThreadId();
    v32 = 34;
    goto LABEL_26;
  }
LABEL_149:
  if ( FileHandle )
    NtClose(FileHandle);
LABEL_151:
  if ( pszDest )
    ExFreePoolWithTag(pszDest, 0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v102 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v103 = PsGetCurrentThreadId();
    WPP_SF_qD(v102, 51, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v103, v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140010620  mov     [rsp-8+arg_18], rbx
0x140010625  mov     [rsp-8+arg_0], rcx
0x14001062a  push    rbp
0x14001062b  push    rsi
0x14001062c  push    rdi
0x14001062d  push    r12
0x14001062f  push    r13
0x140010631  push    r14
0x140010633  push    r15
0x140010635  lea     rbp, [rsp-1Fh]
0x14001063a  sub     rsp, 0F0h
0x140010641  mov     r12, [rdx+48h]
0x140010645  xor     esi, esi
0x140010647  mov     r14, r8
0x14001064a  mov     r15, rdx
0x14001064d  mov     r13, rcx
0x140010650  test    r12, r12
0x140010653  jnz     short loc_14001065B
0x140010655  mov     [rbp+4Fh+var_88], rsi
0x140010659  jmp     short loc_140010664
0x14001065b  mov     rax, [r12+30h]
0x140010660  mov     [rbp+4Fh+var_88], rax
0x140010664  xorps   xmm0, xmm0
0x140010667  mov     [rbp+4Fh+FileHandle], rsi
0x14001066b  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x14001066f  mov     qword ptr [rbp+4Fh+DestinationString.Length], rsi
0x140010673  xor     eax, eax
0x140010675  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x140010679  mov     [rbp+4Fh+DestinationString.Buffer], rsi
0x14001067d  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x140010681  mov     [rbp+4Fh+pszDest], rsi
0x140010685  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x140010689  mov     rbx, cs:WPP_GLOBAL_Control
0x140010690  lea     rdi, WPP_GLOBAL_Control
0x140010697  cmp     rbx, rdi
0x14001069a  jz      short loc_140010712
0x14001069c  test    dword ptr [rbx+2Ch], 4000h
0x1400106a3  jz      short loc_1400106CC
0x1400106a5  mov     rbx, [rbx+18h]
0x1400106a9  call    cs:__imp_PsGetCurrentThreadId
0x1400106b0  nop     dword ptr [rax+rax+00h]
0x1400106b5  mov     edx, 1Bh
0x1400106ba  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x1400106c1  mov     r9, rax
0x1400106c4  mov     rcx, rbx
0x1400106c7  call    WPP_SF_q
0x1400106cc  mov     rbx, cs:WPP_GLOBAL_Control
0x1400106d3  cmp     rbx, rdi
0x1400106d6  jz      short loc_140010712
0x1400106d8  test    dword ptr [rbx+2Ch], 2000h
0x1400106df  jz      short loc_140010712
0x1400106e1  mov     rbx, [rbx+18h]
0x1400106e5  call    cs:__imp_PsGetCurrentThreadId
0x1400106ec  nop     dword ptr [rax+rax+00h]
0x1400106f1  mov     edx, 1Ch
0x1400106f6  mov     qword ptr [rsp+120h+FileAttributes], r15
0x1400106fb  mov     r9, rax
0x1400106fe  mov     [rsp+120h+AllocationSize], r13
0x140010703  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x14001070a  mov     rcx, rbx
0x14001070d  call    WPP_SF_qqq
0x140010712  cmp     dword ptr [r13+2E8h], 11h
0x14001071a  jz      loc_140010B88
0x140010720  mov     dword ptr [r14+30h], 0Dh
0x140010728  mov     rax, [r12+20h]
0x14001072d  mov     rcx, [rax+78h]
0x140010731  mov     rax, [r12+28h]
0x140010736  mov     [rbp+4Fh+Src], rcx
0x14001073a  mov     rsi, [rax+28h]
0x14001073e  mov     [rbp+4Fh+ClientContext], rsi
0x140010742  mov     rsi, cs:WPP_GLOBAL_Control
0x140010749  cmp     rsi, rdi
0x14001074c  jz      loc_140010845
0x140010752  test    dword ptr [rsi+2Ch], 4000h
0x140010759  jz      short loc_1400107A1
0x14001075b  mov     rax, [rcx+20h]
0x14001075f  mov     rsi, [rsi+18h]
0x140010763  mov     rdi, [rax+40h]
0x140010767  movzx   ebx, word ptr [rdi]
0x14001076a  call    cs:__imp_PsGetCurrentThreadId
0x140010771  nop     dword ptr [rax+rax+00h]
0x140010776  mov     edx, 1Dh
0x14001077b  mov     [rsp+120h+FileAttributes], ebx
0x14001077f  mov     r9, rax
0x140010782  mov     [rsp+120h+AllocationSize], rdi
0x140010787  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x14001078e  mov     rcx, rsi
0x140010791  call    WPP_SF_qZd
0x140010796  mov     rcx, [rbp+4Fh+Src]
0x14001079a  lea     rdi, WPP_GLOBAL_Control
0x1400107a1  mov     rsi, cs:WPP_GLOBAL_Control
0x1400107a8  cmp     rsi, rdi
0x1400107ab  jz      loc_140010845
0x1400107b1  test    dword ptr [rsi+2Ch], 4000h
0x1400107b8  jz      short loc_1400107F8
0x1400107ba  mov     rdi, [rcx+58h]
0x1400107be  mov     rsi, [rsi+18h]
0x1400107c2  movzx   ebx, word ptr [rdi]
0x1400107c5  call    cs:__imp_PsGetCurrentThreadId
0x1400107cc  nop     dword ptr [rax+rax+00h]
0x1400107d1  mov     edx, 1Eh
0x1400107d6  mov     [rsp+120h+FileAttributes], ebx
0x1400107da  mov     r9, rax
0x1400107dd  mov     [rsp+120h+AllocationSize], rdi
0x1400107e2  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x1400107e9  mov     rcx, rsi
0x1400107ec  call    WPP_SF_qZd
0x1400107f1  lea     rdi, WPP_GLOBAL_Control
0x1400107f8  mov     rsi, cs:WPP_GLOBAL_Control
0x1400107ff  cmp     rsi, rdi
0x140010802  jz      short loc_140010845
0x140010804  test    dword ptr [rsi+2Ch], 4000h
0x14001080b  jz      short loc_140010845
0x14001080d  mov     rdi, [r12+50h]
0x140010812  mov     rsi, [rsi+18h]
0x140010816  movzx   ebx, word ptr [rdi]
0x140010819  call    cs:__imp_PsGetCurrentThreadId
0x140010820  nop     dword ptr [rax+rax+00h]
0x140010825  mov     edx, 1Fh
0x14001082a  mov     [rsp+120h+FileAttributes], ebx
0x14001082e  mov     r9, rax
0x140010831  mov     [rsp+120h+AllocationSize], rdi
0x140010836  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x14001083d  mov     rcx, rsi
0x140010840  call    WPP_SF_qZd
0x140010845  mov     rax, [r12+28h]
0x14001084a  mov     rcx, [rax+20h]
0x14001084e  xor     eax, eax
0x140010850  mov     rbx, [rcx+20h]
0x140010854  test    rbx, rbx
0x140010857  jz      short loc_14001085D
0x140010859  mov     rax, [rbx+20h]
0x14001085d  mov     [rbp+4Fh+var_90], rax
0x140010861  mov     rcx, r13
0x140010864  mov     rax, [rbx+40h]
0x140010868  movzx   esi, word ptr [rax]
0x14001086b  add     rsi, 2
0x14001086f  mov     rdx, rsi
0x140010872  call    UMRxAllocateSecondaryBuffer
0x140010877  mov     rdi, rax
0x14001087a  test    rax, rax
0x14001087d  jnz     short loc_1400108DA
0x14001087f  mov     esi, 0C000009Ah
0x140010884  mov     rbx, cs:WPP_GLOBAL_Control
0x14001088b  lea     r15, WPP_GLOBAL_Control
0x140010892  cmp     rbx, r15
0x140010895  jz      loc_1400113A6
0x14001089b  test    dword ptr [rbx+2Ch], 2000h
0x1400108a2  jz      loc_1400113A6
0x1400108a8  mov     rbx, [rbx+18h]
0x1400108ac  call    cs:__imp_PsGetCurrentThreadId
0x1400108b3  nop     dword ptr [rax+rax+00h]
0x1400108b8  lea     edx, [rdi+20h]
0x1400108bb  mov     dword ptr [rsp+120h+AllocationSize], 0C000009Ah
0x1400108c3  mov     r9, rax
0x1400108c6  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x1400108cd  mov     rcx, rbx
0x1400108d0  call    WPP_SF_qD
0x1400108d5  jmp     loc_1400113A6
0x1400108da  mov     rdx, [rbx+40h]
0x1400108de  mov     rcx, rdi; void *
0x1400108e1  movzx   r8d, word ptr [rdx]; Size
0x1400108e5  mov     rdx, [rdx+8]; Src
0x1400108e9  call    memmove
0x1400108ee  shr     rsi, 1
0x1400108f1  xor     eax, eax
0x1400108f3  mov     [rdi+rsi*2-2], ax
0x1400108f8  mov     [r14+280h], rdi
0x1400108ff  mov     rbx, cs:WPP_GLOBAL_Control
0x140010906  lea     rax, WPP_GLOBAL_Control
0x14001090d  cmp     rbx, rax
0x140010910  jz      short loc_140010947
0x140010912  test    dword ptr [rbx+2Ch], 4000h
0x140010919  jz      short loc_140010947
0x14001091b  mov     rbx, [rbx+18h]
0x14001091f  call    cs:__imp_PsGetCurrentThreadId
0x140010926  nop     dword ptr [rax+rax+00h]
0x14001092b  mov     edx, 21h ; '!'
0x140010930  mov     [rsp+120h+AllocationSize], rdi
0x140010935  mov     r9, rax
0x140010938  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x14001093f  mov     rcx, rbx
0x140010942  call    WPP_SF_qS
0x140010947  mov     rax, [rbp+4Fh+var_90]
0x14001094b  mov     edx, 5Ch ; '\'; Ch
0x140010950  mov     eax, [rax]
0x140010952  mov     [r14+288h], eax
0x140010959  mov     rax, [rbp+4Fh+Src]
0x14001095d  mov     r8, [rax+58h]
0x140010961  mov     rax, [rax+20h]
0x140010965  movzx   esi, word ptr [r8]
0x140010969  mov     rcx, [rax+40h]
0x14001096d  movzx   eax, word ptr [rcx]
0x140010970  mov     rcx, [r8+8]
0x140010974  sub     esi, eax
0x140010976  add     rcx, 2; Str
0x14001097a  call    cs:__imp_wcschr
0x140010981  nop     dword ptr [rax+rax+00h]
0x140010986  mov     [rbp+4Fh+Src], rax
0x14001098a  mov     rcx, r13
0x14001098d  mov     rax, [r12+50h]
0x140010992  movzx   eax, word ptr [rax]
0x140010995  add     eax, 2
0x140010998  add     eax, esi
0x14001099a  mov     edx, eax
0x14001099c  mov     ebx, eax
0x14001099e  call    UMRxAllocateSecondaryBuffer
0x1400109a3  mov     rdi, rax
0x1400109a6  test    rax, rax
0x1400109a9  jnz     short loc_1400109EC
0x1400109ab  mov     esi, 0C000009Ah
0x1400109b0  mov     rbx, cs:WPP_GLOBAL_Control
0x1400109b7  lea     rax, WPP_GLOBAL_Control
0x1400109be  cmp     rbx, rax
0x1400109c1  jz      loc_1400113A6
0x1400109c7  test    dword ptr [rbx+2Ch], 2000h
0x1400109ce  jz      loc_1400113A6
0x1400109d4  mov     rbx, [rbx+18h]
0x1400109d8  call    cs:__imp_PsGetCurrentThreadId
0x1400109df  nop     dword ptr [rax+rax+00h]
0x1400109e4  lea     edx, [rdi+22h]
0x1400109e7  jmp     loc_1400108BB
0x1400109ec  mov     r8, rbx; Size
0x1400109ef  xor     edx, edx; Val
0x1400109f1  mov     rcx, rdi; void *
0x1400109f4  call    memset
0x1400109f9  mov     rdx, [rbp+4Fh+Src]; Src
0x1400109fd  mov     rcx, rdi; void *
0x140010a00  mov     r8d, esi; Size
0x140010a03  call    memmove
0x140010a08  mov     rdx, [r12+50h]
0x140010a0d  mov     eax, esi
0x140010a0f  shr     rax, 1
0x140010a12  movzx   r8d, word ptr [rdx]; Size
0x140010a16  mov     rdx, [rdx+8]; Src
0x140010a1a  lea     rcx, [rdi+rax*2]; void *
0x140010a1e  call    memmove
0x140010a23  shr     rbx, 1
0x140010a26  xor     esi, esi
0x140010a28  mov     [rdi+rbx*2-2], si
0x140010a2d  mov     [r14+290h], rdi
0x140010a34  mov     rbx, cs:WPP_GLOBAL_Control
0x140010a3b  lea     rax, WPP_GLOBAL_Control
0x140010a42  cmp     rbx, rax
0x140010a45  jz      short loc_140010A7A
0x140010a47  test    dword ptr [rbx+2Ch], 4000h
0x140010a4e  jz      short loc_140010A7A
0x140010a50  mov     rbx, [rbx+18h]
0x140010a54  call    cs:__imp_PsGetCurrentThreadId
0x140010a5b  nop     dword ptr [rax+rax+00h]
0x140010a60  lea     edx, [rsi+23h]
0x140010a63  mov     [rsp+120h+AllocationSize], rdi
0x140010a68  mov     r9, rax
0x140010a6b  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x140010a72  mov     rcx, rbx
0x140010a75  call    WPP_SF_qS
0x140010a7a  mov     rdi, [rbp+4Fh+ClientContext]
0x140010a7e  mov     eax, [rdi+50h]
0x140010a81  mov     [r14+278h], eax
0x140010a88  mov     eax, [rdi+54h]
0x140010a8b  mov     [r14+27Ch], eax
0x140010a92  mov     rbx, cs:WPP_GLOBAL_Control
0x140010a99  lea     rax, WPP_GLOBAL_Control
0x140010aa0  cmp     rbx, rax
0x140010aa3  jz      loc_140010BAE
0x140010aa9  test    dword ptr [rbx+2Ch], 4000h
0x140010ab0  jz      short loc_140010ADE
0x140010ab2  mov     rbx, [rbx+18h]
0x140010ab6  call    cs:__imp_PsGetCurrentThreadId
0x140010abd  nop     dword ptr [rax+rax+00h]
0x140010ac2  mov     edx, 24h ; '$'
0x140010ac7  mov     [rsp+120h+AllocationSize], rdi
0x140010acc  mov     r9, rax
0x140010acf  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x140010ad6  mov     rcx, rbx
0x140010ad9  call    WPP_SF_qq
0x140010ade  mov     rdi, cs:WPP_GLOBAL_Control
0x140010ae5  lea     rax, WPP_GLOBAL_Control
0x140010aec  cmp     rdi, rax
0x140010aef  jz      loc_140010B82
0x140010af5  test    dword ptr [rdi+2Ch], 4000h
0x140010afc  mov     rsi, [rbp+4Fh+ClientContext]
0x140010b00  jz      short loc_140010B30
0x140010b02  mov     ebx, [rsi+50h]
0x140010b05  mov     rdi, [rdi+18h]
0x140010b09  call    cs:__imp_PsGetCurrentThreadId
0x140010b10  nop     dword ptr [rax+rax+00h]
0x140010b15  mov     edx, 25h ; '%'
0x140010b1a  mov     dword ptr [rsp+120h+AllocationSize], ebx
0x140010b1e  mov     r9, rax
0x140010b21  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x140010b28  mov     rcx, rdi
0x140010b2b  call    WPP_SF_qD
0x140010b30  mov     rdi, cs:WPP_GLOBAL_Control
0x140010b37  lea     rax, WPP_GLOBAL_Control
0x140010b3e  cmp     rdi, rax
0x140010b41  jz      short loc_140010B7A
0x140010b43  test    dword ptr [rdi+2Ch], 4000h
0x140010b4a  jz      short loc_140010B7A
0x140010b4c  mov     ebx, [rsi+54h]
  ... truncated ...
```
