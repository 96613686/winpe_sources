# BuildCalEraFromReg

- ea: `0x18010c464`
- end: `0x18010cce6`
- name: `BuildCalEraFromReg`
- size: `2178`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x1800761ec`

## callees

- `0x180078a10`
- `0x18007caa0`
- `0x18007cf00`
- `0x18010c464`
- `0x18012bbc0`
- `0x180146ae4`
- `0x180146b80`
- `0x180146cb0`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18010ca97`
- `ntdll!RtlInitUnicodeString` at `0x18010cb05`
- `ntdll!RtlInitUnicodeString` at `0x18010cbb5`
- `ntdll!RtlInitUnicodeString` at `0x18010ca97`
- `ntdll!RtlInitUnicodeString` at `0x18010cb05`
- `ntdll!RtlInitUnicodeString` at `0x18010cbb5`
- `ntdll!RtlSetLastWin32Error` at `0x18010c586`
- `ntdll!RtlSetLastWin32Error` at `0x18010c586`
- `ntdll!NtOpenKey` at `0x18010cad5`
- `ntdll!NtOpenKey` at `0x18010cbf3`
- `ntdll!NtOpenKey` at `0x18010cad5`
- `ntdll!NtOpenKey` at `0x18010cbf3`
- `ntdll!NtQueryValueKey` at `0x18010cb3f`
- `ntdll!NtQueryValueKey` at `0x18010cb3f`
- `ntdll!NtEnumerateValueKey` at `0x18010c5d5`
- `ntdll!NtEnumerateValueKey` at `0x18010c67c`
- `ntdll!NtEnumerateValueKey` at `0x18010c5d5`
- `ntdll!NtEnumerateValueKey` at `0x18010c67c`
- `ntdll!RtlTimeFieldsToTime` at `0x18010c82e`
- `ntdll!RtlTimeFieldsToTime` at `0x18010c82e`
- `ntdll!NtClose` at `0x18010cca6`
- `ntdll!NtClose` at `0x18010ccb7`
- `ntdll!NtClose` at `0x18010cca6`
- `ntdll!NtClose` at `0x18010ccb7`
- `ntdll!RtlAllocateHeap` at `0x18010c61f`
- `ntdll!RtlAllocateHeap` at `0x18010c85e`
- `ntdll!RtlAllocateHeap` at `0x18010c894`
- `ntdll!RtlAllocateHeap` at `0x18010c8cd`
- `ntdll!RtlAllocateHeap` at `0x18010c906`
- `ntdll!RtlAllocateHeap` at `0x18010c946`
- `ntdll!RtlAllocateHeap` at `0x18010c61f`
- `ntdll!RtlAllocateHeap` at `0x18010c85e`
- `ntdll!RtlAllocateHeap` at `0x18010c894`
- `ntdll!RtlAllocateHeap` at `0x18010c8cd`
- `ntdll!RtlAllocateHeap` at `0x18010c906`
- `ntdll!RtlAllocateHeap` at `0x18010c946`

## string_xrefs

- `0x18010c4f7`: `\Registry\Machine\System\CurrentControlSet\Control`
- `0x18010cb56`: `\Registry\Machine\System\CurrentControlSet\Control`

## pseudocode

```c
_WORD *BuildCalEraFromReg()
{
  unsigned __int64 v0; // rbp
  __int64 v1; // r15
  bool v2; // cc
  int v3; // r14d
  __int64 v4; // rdx
  _WORD *v5; // rbx
  _WORD *v6; // r13
  ULONG v7; // edi
  void *v8; // rcx
  void *v9; // rcx
  NTSTATUS v11; // eax
  _WORD *Heap; // rax
  ULONG v13; // eax
  __int64 v14; // r14
  __int64 v15; // r12
  NTSTATUS v16; // eax
  _WORD *v17; // rsi
  unsigned int v18; // r8d
  _WORD *v19; // rdi
  unsigned __int64 v20; // rdx
  _WORD *v21; // r13
  unsigned int v22; // ecx
  __int16 v23; // ax
  PVOID v24; // rax
  PVOID v25; // rax
  PVOID v26; // rax
  PVOID v27; // rax
  __int64 v28; // rsi
  PVOID v29; // rax
  __int16 v30; // dx
  const wchar_t *v31; // r8
  NTSTATUS v32; // eax
  unsigned int v33; // esi
  ULONG i; // edx
  _WORD v35[2]; // [rsp+50h] [rbp+0h] BYREF

  v0 = (unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL;
  LODWORD(v1) = 0;
  *(_QWORD *)(v0 + 24) = 0;
  *(_QWORD *)(v0 + 40) = 0;
  *(_DWORD *)(v0 + 12) = 0;
  *(_WORD *)(v0 + 8) = 0;
  v2 = (unsigned __int16)word_1803A6BAE >= 3u;
  *(_WORD *)v0 = 0;
  *(_WORD *)(v0 + 4) = 0;
  if ( v2 && qword_1803A6BD8 && (v4 = qword_1803A6BD8 + 2 * (unsigned int)(unsigned __int16)word_1803A6BB2) != 0 )
  {
    v3 = *(unsigned __int16 *)(qword_1803AAD98 + 2LL * *(unsigned int *)(v4 + 20));
    *(_DWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x24) = v3;
  }
  else
  {
    LOWORD(v3) = 0;
    *(_DWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x24) = 0;
  }
  *(_OWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60) = 0;
  *(_OWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x6C) = 0;
  *(_OWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0xA0) = 0;
  *(_OWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) = 0;
  *(_OWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0xB0) = 0;
  if ( StringCchCopyW((STRSAFE_LPWSTR)(v0 + 736), 0x200u, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control") < 0
    || StringCchCatW((STRSAFE_LPWSTR)(v0 + 736), 0x200u, L"\\Nls\\Calendars\\Japanese") < 0 )
  {
    v5 = 0;
    v6 = 0;
LABEL_9:
    v7 = 6;
    goto LABEL_10;
  }
  RtlInitUnicodeString((PUNICODE_STRING)(v0 + 176), (PCWSTR)(v0 + 736));
  *(_DWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) = 48;
  *(_QWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60) = ((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL)
                                                                      + 176;
  *(_QWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58) = 0;
  *(_DWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x68) = 64;
  *(_OWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x70) = 0;
  v32 = NtOpenKey((PHANDLE)(v0 + 40), 0x20019u, (POBJECT_ATTRIBUTES)(v0 + 80));
  if ( v32 < 0 )
    *(_QWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
  v5 = 0;
  v6 = 0;
  if ( v32 < 0 )
    goto LABEL_9;
  RtlInitUnicodeString((PUNICODE_STRING)(v0 + 160), L"InitialEraYear");
  if ( NtQueryValueKey(
         *(HANDLE *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28),
         (PUNICODE_STRING)(v0 + 160),
         KeyValueFullInformation,
         (PVOID)(v0 + 192),
         0x214u,
         (PULONG)(v0 + 12)) >= 0
    && (*(_DWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0xCC) >> 1)
     - (*(_WORD *)(*(unsigned int *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC8)
                 + ((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL)
                 + 0xC0
                 + 2LL * (unsigned int)((*(_DWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0xCC) >> 1) - 1)) == 0) == 2
    && *(_WORD *)(*(unsigned int *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC8)
                + ((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL)
                + 0xC0) == 49
    && *(_WORD *)(*(unsigned int *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC8)
                + ((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL)
                + 0xC0
                + 2) == 24180 )
  {
    gPreferNumericInitialJapaneseEra = 1;
  }
  *(_OWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60) = 0;
  *(_OWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x6C) = 0;
  *(_OWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) = 0;
  *(_OWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0xB0) = 0;
  if ( StringCchCopyW((STRSAFE_LPWSTR)(v0 + 736), 0x200u, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control") < 0
    || StringCchCatW((STRSAFE_LPWSTR)(v0 + 736), 0x200u, L"\\Nls\\Calendars\\Japanese\\Eras") < 0 )
  {
    goto LABEL_9;
  }
  RtlInitUnicodeString((PUNICODE_STRING)(v0 + 176), (PCWSTR)(v0 + 736));
  *(_DWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) = 48;
  *(_QWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60) = ((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL)
                                                                      + 176;
  *(_QWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58) = 0;
  *(_DWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x68) = 64;
  *(_OWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x70) = 0;
  if ( NtOpenKey((PHANDLE)(v0 + 24), 0x20019u, (POBJECT_ATTRIBUTES)(v0 + 80)) < 0 )
  {
    *(_QWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
    goto LABEL_9;
  }
  v33 = 0;
  for ( i = 0; ; i = v33 )
  {
    v11 = NtEnumerateValueKey(
            *(HANDLE *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18),
            i,
            KeyValueFullInformation,
            (PVOID)(v0 + 192),
            0x214u,
            (PULONG)(v0 + 12));
    if ( v11 < 0 )
      break;
    ++v33;
  }
  if ( v11 == -2147483622 )
  {
    v7 = 0;
    if ( v33 >= (unsigned __int16)v3 )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 8LL * (v33 + 1));
      *(_QWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80) = Heap;
      v5 = Heap;
      if ( Heap )
      {
        v13 = 0;
        *(_QWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = 0;
        *(_QWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = 0;
        LODWORD(v14) = 0;
        *(_QWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48) = 0;
        LODWORD(v15) = 0;
        v6 = v5;
        while ( 1 )
        {
          *(_DWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = v13;
          v16 = NtEnumerateValueKey(
                  *(HANDLE *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18),
                  v13,
                  KeyValueFullInformation,
                  (PVOID)(v0 + 192),
                  0x214u,
                  (PULONG)(v0 + 12));
          if ( v16 < 0 )
            break;
          v17 = (_WORD *)(*(unsigned int *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC8)
                        + ((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL)
                        + 192);
          if ( (*(_DWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0xD0) >> 1)
             - (*(_WORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL)
                         + 0xD4
                         + 2LL
                         * (unsigned int)((*(_DWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0xD0) >> 1) - 1)) == 0) == 10 )
          {
            v18 = (*(_DWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0xCC) >> 1)
                - (*(_WORD *)(*(unsigned int *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC8)
                            + ((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL)
                            + 0xC0
                            + 2LL
                            * (unsigned int)((*(_DWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0xCC) >> 1)
                                           - 1)) == 0);
            if ( v18 >= 7 && *(_DWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC4) == 1 )
            {
              v19 = *(_WORD **)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38);
              v20 = *(unsigned int *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC8)
                  + ((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL)
                  + 192;
              v21 = *(_WORD **)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40);
              v22 = 0;
              *(_QWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x98) = v17;
              do
              {
                if ( *v17 == 95 )
                {
                  ++v22;
                  *v17 = 0;
                  switch ( v22 )
                  {
                    case 1u:
                      v19 = v17 + 1;
                      v15 = (__int64)((__int64)v17 - v20) >> 1;
                      break;
                    case 2u:
                      v21 = v17 + 1;
                      v1 = v17 - v19;
                      break;
                    case 3u:
                      *(_QWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48) = v17 + 1;
                      v14 = v17 - v21;
                      break;
                  }
                }
                ++v17;
                --v18;
              }
              while ( v18 );
              v5 = *(_WORD **)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80);
              *(_QWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = v21;
              v6 = v5;
              *(_QWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = v19;
              v7 = 0;
              if ( v22 >= 3 )
              {
                if ( (unsigned int)ConvertDecimalToWord(v0 + 212, 4, v0 + 8) )
                {
                  if ( (unsigned int)ConvertDecimalToWord(v0 + 222, 2, (unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) )
                  {
                    if ( (unsigned int)ConvertDecimalToWord(v0 + 228, 2, v0 + 4) )
                    {
                      v23 = *(_WORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
                      *(_WORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = v23;
                      *(_WORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0xB0) = v23;
                      *(_WORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0xB2) = *(_WORD *)((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL);
                      *(_WORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0xB4) = *(_WORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 4);
                      *(_QWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x90) = 0;
                      *(_DWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0xBC) = 0;
                      *(_DWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0xB6) = 0;
                      *(_WORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0xBA) = 0;
                      if ( RtlTimeFieldsToTime((PTIME_FIELDS)(v0 + 176), (PLARGE_INTEGER)(v0 + 144)) )
                      {
                        ++*v5;
                        v24 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x30u);
                        *(_QWORD *)&v5[4 * (unsigned __int16)*v5] = v24;
                        if ( !v24 )
                          goto LABEL_62;
                        v25 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v15 + 2));
                        *(_QWORD *)(*(_QWORD *)&v5[4 * (unsigned __int16)*v5] + 16LL) = v25;
                        if ( !v25
                          || (v26 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v1 + 2)),
                              (*(_QWORD *)(*(_QWORD *)&v5[4 * (unsigned __int16)*v5] + 24LL) = v26) == 0)
                          || (v27 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v14 + 2)),
                              (*(_QWORD *)(*(_QWORD *)&v5[4 * (unsigned __int16)*v5] + 32LL) = v27) == 0)
                          || (v28 = ((__int64)v17 - *(_QWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48)) >> 1,
                              v29 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v28 + 2)),
                              (*(_QWORD *)(*(_QWORD *)&v5[4 * (unsigned __int16)*v5] + 40LL) = v29) == 0) )
                        {
LABEL_62:
                          v7 = 8;
                          goto LABEL_10;
                        }
                        v30 = *(_WORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10);
                        **(_WORD **)&v5[4 * (unsigned __int16)*v5] = 7;
                        *(_WORD *)(*(_QWORD *)&v5[4 * (unsigned __int16)*v5] + 4LL) = v30;
                        *(_WORD *)(*(_QWORD *)&v5[4 * (unsigned __int16)*v5] + 6LL) = *(_WORD *)v0;
                        *(_WORD *)(*(_QWORD *)&v5[4 * (unsigned __int16)*v5] + 8LL) = *(_WORD *)(((unsigned __int64)v35
                                                                                                & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                               + 4);
                        *(_WORD *)(*(_QWORD *)&v5[4 * (unsigned __int16)*v5] + 10LL) = v30 - 1;
                        *(_WORD *)(*(_QWORD *)&v5[4 * (unsigned __int16)*v5] + 12LL) = 1;
                        v31 = *(const wchar_t **)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x98);
                        **(_WORD **)(*(_QWORD *)&v5[4 * (unsigned __int16)*v5] + 16LL) = v15;
                        **(_WORD **)(*(_QWORD *)&v5[4 * (unsigned __int16)*v5] + 24LL) = v1;
                        **(_WORD **)(*(_QWORD *)&v5[4 * (unsigned __int16)*v5] + 32LL) = v14;
                        **(_WORD **)(*(_QWORD *)&v5[4 * (unsigned __int16)*v5] + 40LL) = v28;
                        StringCchCopyNW(
                          (STRSAFE_LPWSTR)(*(_QWORD *)(*(_QWORD *)&v5[4 * (unsigned __int16)*v5] + 16LL) + 2LL),
                          (unsigned int)(v15 + 1),
                          v31,
                          (unsigned int)(v15 + 1));
                        StringCchCopyNW(
                          (STRSAFE_LPWSTR)(*(_QWORD *)(*(_QWORD *)&v5[4 * (unsigned __int16)*v5] + 24LL) + 2LL),
                          (unsigned int)(v1 + 1),
                          *(STRSAFE_PCNZWCH *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38),
                          (unsigned int)(v1 + 1));
                        StringCchCopyNW(
                          (STRSAFE_LPWSTR)(*(_QWORD *)(*(_QWORD *)&v5[4 * (unsigned __int16)*v5] + 32LL) + 2LL),
                          (unsigned int)(v14 + 1),
                          *(STRSAFE_PCNZWCH *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40),
                          (unsigned int)(v14 + 1));
                        StringCchCopyNW(
                          (STRSAFE_LPWSTR)(*(_QWORD *)(*(_QWORD *)&v5[4 * (unsigned __int16)*v5] + 40LL) + 2LL),
                          (unsigned int)(v28 + 1),
                          *(STRSAFE_PCNZWCH *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48),
                          (unsigned int)(v28 + 1));
                      }
                    }
                  }
                }
              }
            }
          }
          v13 = *(_DWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) + 1;
        }
        if ( v16 == -2147483622 )
        {
          EraBubbleSort(v5);
          IndexEras(v5);
        }
        else
        {
          v7 = 1009;
        }
      }
      else
      {
        v7 = 8;
      }
    }
  }
  else
  {
    v7 = 1009;
  }
LABEL_10:
  v8 = *(void **)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
  if ( v8 )
    NtClose(v8);
  v9 = *(void **)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28);
  if ( v9 )
    NtClose(v9);
  if ( v7 || v5 && *v6 < (unsigned __int16)*(_DWORD *)(((unsigned __int64)v35 & 0xFFFFFFFFFFFFFFE0uLL) + 0x24) )
  {
    FreeCalendarEraMem(v5);
    v5 = 0;
  }
  RtlSetLastWin32Error(v7);
  return v5;
}

```

## disassembly

```asm
0x18010c464  push    rbp
0x18010c466  push    rbx
0x18010c467  push    rsi
0x18010c468  push    rdi
0x18010c469  push    r12
0x18010c46b  push    r13
0x18010c46d  push    r14
0x18010c46f  push    r15
0x18010c471  sub     rsp, 748h
0x18010c478  lea     rbp, [rsp+50h]
0x18010c47d  and     rbp, 0FFFFFFFFFFFFFFE0h
0x18010c481  mov     rax, cs:__security_cookie
0x18010c488  xor     rax, rsp
0x18010c48b  mov     [rbp+730h+var_50], rax
0x18010c492  xor     r15d, r15d
0x18010c495  mov     [rbp+730h+KeyHandle], r15
0x18010c499  mov     [rbp+730h+Handle], r15
0x18010c49d  mov     [rbp+730h+var_724], r15d
0x18010c4a1  lea     eax, [r15+3]
0x18010c4a5  mov     [rbp+730h+var_728], r15w
0x18010c4aa  cmp     ax, cs:word_1803A6BAE
0x18010c4b1  mov     [rbp+730h+var_730], r15w
0x18010c4b6  mov     [rbp+730h+var_72C], r15w
0x18010c4bb  ja      short loc_18010C4C9
0x18010c4bd  mov     rcx, cs:qword_1803A6BD8
0x18010c4c4  test    rcx, rcx
0x18010c4c7  jnz     short loc_18010C4D2
0x18010c4c9  mov     r14d, r15d
0x18010c4cc  mov     [rbp+730h+var_70C], r15d
0x18010c4d0  jmp     short loc_18010C4F4
0x18010c4d2  movzx   eax, cs:word_1803A6BB2
0x18010c4d9  lea     edx, [rax+rax]
0x18010c4dc  add     rdx, rcx
0x18010c4df  jz      short loc_18010C4C9
0x18010c4e1  mov     ecx, [rdx+14h]
0x18010c4e4  mov     rax, cs:qword_1803AAD98
0x18010c4eb  movzx   r14d, word ptr [rax+rcx*2]
0x18010c4f0  mov     [rbp+730h+var_70C], r14d
0x18010c4f4  xorps   xmm0, xmm0
0x18010c4f7  lea     r8, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x18010c4fe  movups  xmmword ptr [rbp+730h+ObjectAttributes.ObjectName], xmm0
0x18010c502  mov     esi, 200h
0x18010c507  lea     rcx, [rbp+730h+pszDest]; pszDest
0x18010c50e  mov     edx, esi; cchDest
0x18010c510  xor     eax, eax
0x18010c512  movups  xmmword ptr [rbp+730h+ObjectAttributes+1Ch], xmm0
0x18010c516  movups  xmmword ptr [rbp+730h+DestinationString.Length], xmm0
0x18010c51d  movups  xmmword ptr [rbp+730h+ObjectAttributes.Length], xmm0
0x18010c521  movups  xmmword ptr [rbp+730h+TimeFields.Year], xmm0
0x18010c528  call    StringCchCopyW
0x18010c52d  test    eax, eax
0x18010c52f  js      short loc_18010C54E
0x18010c531  lea     r8, aNlsCalendarsJa; "\\Nls\\Calendars\\Japanese"
0x18010c538  mov     edx, esi; cchDest
0x18010c53a  lea     rcx, [rbp+730h+pszDest]; pszDest
0x18010c541  call    StringCchCatW
0x18010c546  test    eax, eax
0x18010c548  jns     loc_18010CA89
0x18010c54e  mov     rbx, r15
0x18010c551  mov     r13, r15
0x18010c554  mov     edi, 6
0x18010c559  mov     rcx, [rbp+730h+KeyHandle]; Handle
0x18010c55d  test    rcx, rcx
0x18010c560  jnz     loc_18010CCA6
0x18010c566  mov     rcx, [rbp+730h+Handle]; Handle
0x18010c56a  test    rcx, rcx
0x18010c56d  jnz     loc_18010CCB7
0x18010c573  test    edi, edi
0x18010c575  jnz     loc_18010CCD6
0x18010c57b  test    rbx, rbx
0x18010c57e  jnz     loc_18010CCC8
0x18010c584  mov     ecx, edi; LastError
0x18010c586  call    cs:__imp_RtlSetLastWin32Error
0x18010c58d  nop     dword ptr [rax+rax+00h]
0x18010c592  mov     rax, rbx
0x18010c595  mov     rcx, [rbp+730h+var_50]
0x18010c59c  xor     rcx, rsp; StackCookie
0x18010c59f  call    __security_check_cookie
0x18010c5a4  add     rsp, 748h
0x18010c5ab  pop     r15
0x18010c5ad  pop     r14
0x18010c5af  pop     r13
0x18010c5b1  pop     r12
0x18010c5b3  pop     rdi
0x18010c5b4  pop     rsi
0x18010c5b5  pop     rbx
0x18010c5b6  pop     rbp
0x18010c5b7  retn
0x18010c5b9  mov     rcx, [rbp+730h+KeyHandle]; KeyHandle
0x18010c5bd  lea     rax, [rbp+730h+var_724]
0x18010c5c1  mov     [rsp+780h+ResultLength], rax; ResultLength
0x18010c5c6  lea     r9, [rbp+730h+KeyValueInformation]; KeyValueInformation
0x18010c5cd  mov     r8d, edi; KeyValueInformationClass
0x18010c5d0  mov     [rsp+780h+Length], r12d; Length
0x18010c5d5  call    cs:__imp_NtEnumerateValueKey
0x18010c5dc  nop     dword ptr [rax+rax+00h]
0x18010c5e1  test    eax, eax
0x18010c5e3  jns     loc_18010CC6D
0x18010c5e9  cmp     eax, 8000001Ah
0x18010c5ee  jnz     loc_18010CC76
0x18010c5f4  movzx   eax, r14w
0x18010c5f8  mov     edi, r15d
0x18010c5fb  cmp     esi, eax
0x18010c5fd  jb      loc_18010C559
0x18010c603  mov     rcx, gs:60h
0x18010c60c  lea     r8d, [rsi+1]
0x18010c610  mov     esi, 8
0x18010c615  shl     r8, 3; Size
0x18010c619  mov     edx, esi; Flags
0x18010c61b  mov     rcx, [rcx+30h]; HeapHandle
0x18010c61f  call    cs:__imp_RtlAllocateHeap
0x18010c626  nop     dword ptr [rax+rax+00h]
0x18010c62b  mov     [rbp+730h+var_6B0], rax
0x18010c632  mov     rbx, rax
0x18010c635  test    rax, rax
0x18010c638  jz      loc_18010CC80
0x18010c63e  xor     eax, eax
0x18010c640  mov     [rbp+730h+var_6F8], r15
0x18010c644  mov     [rbp+730h+var_6F0], rax
0x18010c648  mov     r14d, eax
0x18010c64b  mov     [rbp+730h+var_6E8], rax
0x18010c64f  mov     r12d, r15d
0x18010c652  mov     r13, rbx
0x18010c655  lea     rcx, [rbp+730h+var_724]
0x18010c659  mov     [rbp+730h+var_710], eax
0x18010c65c  mov     [rsp+780h+ResultLength], rcx; ResultLength
0x18010c661  lea     r9, [rbp+730h+KeyValueInformation]; KeyValueInformation
0x18010c668  mov     rcx, [rbp+730h+KeyHandle]; KeyHandle
0x18010c66c  mov     r8d, 1; KeyValueInformationClass
0x18010c672  mov     edx, eax; Index
0x18010c674  mov     [rsp+780h+Length], 214h; Length
0x18010c67c  call    cs:__imp_NtEnumerateValueKey
0x18010c683  nop     dword ptr [rax+rax+00h]
0x18010c688  xor     r10d, r10d
0x18010c68b  test    eax, eax
0x18010c68d  js      loc_18010C754
0x18010c693  mov     eax, [rbp+730h+var_668]
0x18010c699  lea     rsi, [rbp+730h+KeyValueInformation]
0x18010c6a0  mov     r8d, [rbp+730h+var_664]
0x18010c6a7  add     rsi, rax
0x18010c6aa  mov     edx, [rbp+730h+var_660]
0x18010c6b0  mov     r9d, r10d
0x18010c6b3  shr     edx, 1
0x18010c6b5  shr     r8d, 1
0x18010c6b8  lea     ecx, [rdx-1]
0x18010c6bb  lea     eax, [r8-1]
0x18010c6bf  cmp     [rsi+rax*2], r10w
0x18010c6c4  mov     eax, r10d
0x18010c6c7  setz    r9b
0x18010c6cb  cmp     [rbp+rcx*2+730h+var_65C], r10w
0x18010c6d4  setz    al
0x18010c6d7  sub     edx, eax
0x18010c6d9  cmp     edx, 0Ah
0x18010c6dc  jnz     loc_18010C79F
0x18010c6e2  sub     r8d, r9d
0x18010c6e5  cmp     r8d, 7
0x18010c6e9  jb      loc_18010C79F
0x18010c6ef  cmp     [rbp+730h+var_66C], 1
0x18010c6f6  jnz     loc_18010C79F
0x18010c6fc  mov     rdi, [rbp+730h+var_6F8]
0x18010c700  mov     rdx, rsi
0x18010c703  mov     r13, [rbp+730h+var_6F0]
0x18010c707  mov     ecx, r10d
0x18010c70a  mov     [rbp+730h+pszSrc], rdx
0x18010c711  cmp     word ptr [rsi], 5Fh ; '_'
0x18010c715  jnz     loc_1801A2CEA
0x18010c71b  inc     ecx
0x18010c71d  mov     [rsi], r10w
0x18010c721  mov     eax, ecx
0x18010c723  sub     eax, 1
0x18010c726  jz      loc_1801A2CDD
0x18010c72c  sub     eax, 1
0x18010c72f  jz      loc_1801A2CCE
0x18010c735  cmp     eax, 1
0x18010c738  jnz     loc_1801A2CEA
0x18010c73e  mov     r14, rsi
0x18010c741  lea     rax, [rsi+2]
0x18010c745  sub     r14, r13
0x18010c748  mov     [rbp+730h+var_6E8], rax
0x18010c74c  sar     r14, 1
0x18010c74f  jmp     loc_1801A2CEA
0x18010c754  cmp     eax, 8000001Ah
0x18010c759  jz      loc_18010CC91
0x18010c75f  mov     edi, 3F1h
0x18010c764  xor     r15d, r15d
0x18010c767  jmp     loc_18010C559
0x18010c76c  mov     rbx, [rbp+730h+var_6B0]
0x18010c773  mov     [rbp+730h+var_6F0], r13
0x18010c777  mov     r13, rbx
0x18010c77a  mov     [rbp+730h+var_6F8], rdi
0x18010c77e  mov     edi, r10d
0x18010c781  cmp     ecx, 3
0x18010c784  jb      short loc_18010C79F
0x18010c786  lea     r8, [rbp+730h+var_728]
0x18010c78a  mov     edx, 4
0x18010c78f  lea     rcx, [rbp+730h+var_65C]
0x18010c796  call    ConvertDecimalToWord
0x18010c79b  test    eax, eax
0x18010c79d  jnz     short loc_18010C7A9
0x18010c79f  mov     eax, [rbp+730h+var_710]
0x18010c7a2  inc     eax
0x18010c7a4  jmp     loc_18010C655
0x18010c7a9  lea     r8, [rbp+730h+var_730]
0x18010c7ad  mov     edx, 2
0x18010c7b2  lea     rcx, [rbp+730h+var_652]
0x18010c7b9  call    ConvertDecimalToWord
0x18010c7be  test    eax, eax
0x18010c7c0  jz      short loc_18010C79F
0x18010c7c2  lea     r8, [rbp+730h+var_72C]
0x18010c7c6  mov     edx, 2
0x18010c7cb  lea     rcx, [rbp+730h+var_64C]
0x18010c7d2  call    ConvertDecimalToWord
0x18010c7d7  xor     r10d, r10d
0x18010c7da  test    eax, eax
0x18010c7dc  jz      short loc_18010C79F
0x18010c7de  movzx   eax, [rbp+730h+var_728]
0x18010c7e2  lea     rdx, [rbp+730h+Time]; Time
0x18010c7e9  mov     [rbp+730h+var_720], ax
0x18010c7ed  lea     rcx, [rbp+730h+TimeFields]; TimeFields
0x18010c7f4  mov     [rbp+730h+TimeFields.Year], ax
0x18010c7fb  movzx   eax, [rbp+730h+var_730]
0x18010c7ff  mov     [rbp+730h+TimeFields.Month], ax
0x18010c806  movzx   eax, [rbp+730h+var_72C]
0x18010c80a  mov     [rbp+730h+TimeFields.Day], ax
0x18010c811  mov     qword ptr [rbp+730h+Time], r10
0x18010c818  mov     dword ptr [rbp+730h+TimeFields.Milliseconds], r10d
0x18010c81f  mov     dword ptr [rbp+730h+TimeFields.Hour], r10d
0x18010c826  mov     [rbp+730h+TimeFields.Second], r10w
0x18010c82e  call    cs:__imp_RtlTimeFieldsToTime
0x18010c835  nop     dword ptr [rax+rax+00h]
0x18010c83a  test    al, al
0x18010c83c  jz      loc_18010C79F
0x18010c842  mov     eax, 1
0x18010c847  add     [rbx], ax
0x18010c84a  mov     rcx, gs:60h
0x18010c853  lea     edx, [rax+7]; Flags
0x18010c856  lea     r8d, [rax+2Fh]; Size
0x18010c85a  mov     rcx, [rcx+30h]; HeapHandle
0x18010c85e  call    cs:__imp_RtlAllocateHeap
0x18010c865  nop     dword ptr [rax+rax+00h]
0x18010c86a  movzx   ecx, word ptr [rbx]
0x18010c86d  mov     [rbx+rcx*8], rax
0x18010c871  test    rax, rax
0x18010c874  jz      loc_18010CC87
0x18010c87a  mov     rcx, gs:60h
0x18010c883  lea     r8d, [r12+2]
0x18010c888  add     r8, r8; Size
0x18010c88b  mov     edx, 8; Flags
0x18010c890  mov     rcx, [rcx+30h]; HeapHandle
0x18010c894  call    cs:__imp_RtlAllocateHeap
0x18010c89b  nop     dword ptr [rax+rax+00h]
0x18010c8a0  movzx   ecx, word ptr [rbx]
0x18010c8a3  mov     rdx, [rbx+rcx*8]
0x18010c8a7  mov     [rdx+10h], rax
0x18010c8ab  test    rax, rax
0x18010c8ae  jz      loc_18010CC87
0x18010c8b4  mov     rcx, gs:60h
0x18010c8bd  lea     r8d, [r15+2]
0x18010c8c1  add     r8, r8; Size
0x18010c8c4  mov     edx, 8; Flags
0x18010c8c9  mov     rcx, [rcx+30h]; HeapHandle
0x18010c8cd  call    cs:__imp_RtlAllocateHeap
0x18010c8d4  nop     dword ptr [rax+rax+00h]
0x18010c8d9  movzx   ecx, word ptr [rbx]
0x18010c8dc  mov     rdx, [rbx+rcx*8]
0x18010c8e0  mov     [rdx+18h], rax
0x18010c8e4  test    rax, rax
0x18010c8e7  jz      loc_18010CC87
0x18010c8ed  mov     rcx, gs:60h
0x18010c8f6  lea     r8d, [r14+2]
0x18010c8fa  add     r8, r8; Size
0x18010c8fd  mov     edx, 8; Flags
0x18010c902  mov     rcx, [rcx+30h]; HeapHandle
0x18010c906  call    cs:__imp_RtlAllocateHeap
0x18010c90d  nop     dword ptr [rax+rax+00h]
0x18010c912  movzx   ecx, word ptr [rbx]
0x18010c915  mov     rdx, [rbx+rcx*8]
0x18010c919  mov     [rdx+20h], rax
0x18010c91d  test    rax, rax
0x18010c920  jz      loc_18010CC87
0x18010c926  mov     rcx, gs:60h
0x18010c92f  mov     edx, 8; Flags
0x18010c934  sub     rsi, [rbp+730h+var_6E8]
0x18010c938  sar     rsi, 1
0x18010c93b  mov     rcx, [rcx+30h]; HeapHandle
0x18010c93f  lea     r8d, [rsi+2]
0x18010c943  add     r8, r8; Size
0x18010c946  call    cs:__imp_RtlAllocateHeap
0x18010c94d  nop     dword ptr [rax+rax+00h]
0x18010c952  movzx   ecx, word ptr [rbx]
0x18010c955  mov     rdx, [rbx+rcx*8]
0x18010c959  mov     [rdx+28h], rax
0x18010c95d  test    rax, rax
0x18010c960  jz      loc_18010CC87
0x18010c966  movzx   eax, word ptr [rbx]
0x18010c969  mov     r8d, 1
0x18010c96f  movzx   edx, [rbp+730h+var_720]
0x18010c973  mov     rcx, [rbx+rax*8]
0x18010c977  mov     word ptr [rcx], 7
0x18010c97c  movzx   eax, word ptr [rbx]
  ... truncated ...
```
