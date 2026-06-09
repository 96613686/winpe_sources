# KernelTriageDumpTargetInfo::GetWdfTriageInformation(unsigned __int64)

- ea: `0x18022e688`
- end: `0x18022eb59`
- name: `?GetWdfTriageInformation@KernelTriageDumpTargetInfo@@QEAAJ_K@Z`
- size: `1233`
- prototype: `int(KernelTriageDumpTargetInfo *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180220be8`
- `0x180221b0c`
- `0x180226cc8`
- `0x18022cd18`

## callees

- `0x180071a60`
- `0x1800c1cd8`
- `0x18022e688`
- `0x1804da4c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e73c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e76d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e796`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e7c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e7ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e812`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e83b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e863`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e88b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e73c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e76d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e796`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e7c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e7ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e812`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e83b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e863`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e88b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022e75a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022e783`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022e7af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022e7d7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022e7ff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022e828`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022e850`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022e878`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022e8a0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022e75a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022e783`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022e7af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022e7d7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022e7ff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022e828`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022e850`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022e878`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022e8a0`

## string_xrefs

- `0x18022e6f4`: `KernelTriageDumpTargetInfo::GetWdfTriageInformation::           ==> Failed to read Wdf Triage Information structure\n`
- `0x18022e94d`: `KernelTriageDumpTargetInfo::GetWdfTriageInformation::           ==> Unable to read WdfObjectTriageInfo structure`
- `0x18022e9c4`: `KernelTriageDumpTargetInfo::GetWdfTriageInformation::           ==> Unable to read WdfContextTypeTriageInfo structure`
- `0x18022e98a`: `KernelTriageDumpTargetInfo::GetWdfTriageInformation::           ==> Unable to read WdfContextTriageInfo structure`
- `0x18022ea37`: `KernelTriageDumpTargetInfo::GetWdfTriageInformation::           ==> Unable to read WdfFwdProgressTriageInfo structure`
- `0x18022e9fd`: `KernelTriageDumpTargetInfo::GetWdfTriageInformation::           ==> Unable to read WdfQueueTriageInfo structure`
- `0x18022eaad`: `KernelTriageDumpTargetInfo::GetWdfTriageInformation::           ==> Unable to read WdfRequestTriageInfo structure`
- `0x18022ea74`: `KernelTriageDumpTargetInfo::GetWdfTriageInformation::           ==> Unable to read WdfIrpQueueTriageInfo structure`
- `0x18022eb1b`: `KernelTriageDumpTargetInfo::GetWdfTriageInformation::           ==> Unable to read WdfIrpTriageInfo structure`
- `0x18022eae4`: `KernelTriageDumpTargetInfo::GetWdfTriageInformation::           ==> Unable to read WdfDeviceTriageInfo structure`

## pseudocode

```c
__int64 __fastcall KernelTriageDumpTargetInfo::GetWdfTriageInformation(
        KernelTriageDumpTargetInfo *this,
        unsigned __int64 a2)
{
  unsigned int AllVirtual; // ebx
  HANDLE ProcessHeap; // rax
  HANDLE v7; // rax
  HANDLE v8; // rax
  HANDLE v9; // rax
  HANDLE v10; // rax
  HANDLE v11; // rax
  HANDLE v12; // rax
  HANDLE v13; // rax
  HANDLE v14; // rax
  LPVOID v15; // rax
  void *v16; // r9
  _QWORD v17[18]; // [rsp+30h] [rbp-39h] BYREF

  if ( *((_BYTE *)this + 52424) == 1 )
    return 0;
  memset(v17, 0, 0x60u);
  AllVirtual = TargetInfo::ReadAllVirtual(g_Target, g_Process, a2, v17, 0x60u, 0);
  if ( AllVirtual )
  {
    VerbOut(
      L"KernelTriageDumpTargetInfo::GetWdfTriageInformation::           ==> Failed to read Wdf Triage Information structure\n");
    goto LABEL_36;
  }
  if ( LODWORD(v17[1]) == 1 )
  {
    *((_QWORD *)this + 6541) = v17[0];
    *((_DWORD *)this + 13085) = HIDWORD(v17[1]);
    *((_DWORD *)this + 13084) = 1;
    ProcessHeap = GetProcessHeap();
    *((_QWORD *)this + 6544) = HeapAlloc(ProcessHeap, 8u, 0x1Cu);
    v7 = GetProcessHeap();
    *((_QWORD *)this + 6545) = HeapAlloc(v7, 8u, 0x14u);
    v8 = GetProcessHeap();
    *((_QWORD *)this + 6546) = HeapAlloc(v8, 8u, 0xCu);
    v9 = GetProcessHeap();
    *((_QWORD *)this + 6547) = HeapAlloc(v9, 8u, 0x1Cu);
    v10 = GetProcessHeap();
    *((_QWORD *)this + 6548) = HeapAlloc(v10, 8u, 0xCu);
    v11 = GetProcessHeap();
    *((_QWORD *)this + 6549) = HeapAlloc(v11, 8u, 0x10u);
    v12 = GetProcessHeap();
    *((_QWORD *)this + 6550) = HeapAlloc(v12, 8u, 0x1Cu);
    v13 = GetProcessHeap();
    *((_QWORD *)this + 6551) = HeapAlloc(v13, 8u, 8u);
    v14 = GetProcessHeap();
    v15 = HeapAlloc(v14, 8u, 8u);
    v16 = (void *)*((_QWORD *)this + 6544);
    *((_QWORD *)this + 6552) = v15;
    if ( v16
      && *((_QWORD *)this + 6545)
      && *((_QWORD *)this + 6546)
      && *((_QWORD *)this + 6547)
      && *((_QWORD *)this + 6548)
      && *((_QWORD *)this + 6549)
      && *((_QWORD *)this + 6550)
      && *((_QWORD *)this + 6551)
      && v15 )
    {
      AllVirtual = TargetInfo::ReadAllVirtual(g_Target, g_Process, v17[3], v16, 0x1Cu, 0);
      if ( AllVirtual )
      {
        VerbOut(
          L"KernelTriageDumpTargetInfo::GetWdfTriageInformation::           ==> Unable to read WdfObjectTriageInfo structure");
      }
      else
      {
        AllVirtual = TargetInfo::ReadAllVirtual(g_Target, g_Process, v17[4], *((void **)this + 6545), 0x14u, 0);
        if ( AllVirtual )
        {
          VerbOut(
            L"KernelTriageDumpTargetInfo::GetWdfTriageInformation::           ==> Unable to read WdfContextTriageInfo structure");
        }
        else
        {
          AllVirtual = TargetInfo::ReadAllVirtual(g_Target, g_Process, v17[5], *((void **)this + 6546), 0xCu, 0);
          if ( AllVirtual )
          {
            VerbOut(
              L"KernelTriageDumpTargetInfo::GetWdfTriageInformation::           ==> Unable to read WdfContextTypeTriageInfo structure");
          }
          else
          {
            AllVirtual = TargetInfo::ReadAllVirtual(g_Target, g_Process, v17[6], *((void **)this + 6547), 0x1Cu, 0);
            if ( AllVirtual )
            {
              VerbOut(
                L"KernelTriageDumpTargetInfo::GetWdfTriageInformation::           ==> Unable to read WdfQueueTriageInfo structure");
            }
            else
            {
              AllVirtual = TargetInfo::ReadAllVirtual(g_Target, g_Process, v17[7], *((void **)this + 6548), 0xCu, 0);
              if ( AllVirtual )
              {
                VerbOut(
                  L"KernelTriageDumpTargetInfo::GetWdfTriageInformation::           ==> Unable to read WdfFwdProgressTriageInfo structure");
              }
              else
              {
                AllVirtual = TargetInfo::ReadAllVirtual(g_Target, g_Process, v17[8], *((void **)this + 6549), 0x10u, 0);
                if ( AllVirtual )
                {
                  VerbOut(
                    L"KernelTriageDumpTargetInfo::GetWdfTriageInformation::           ==> Unable to read WdfIrpQueueTriageInfo structure");
                }
                else
                {
                  AllVirtual = TargetInfo::ReadAllVirtual(
                                 g_Target,
                                 g_Process,
                                 v17[9],
                                 *((void **)this + 6550),
                                 0x1Cu,
                                 0);
                  if ( AllVirtual )
                  {
                    VerbOut(
                      L"KernelTriageDumpTargetInfo::GetWdfTriageInformation::           ==> Unable to read WdfRequestTriageInfo structure");
                  }
                  else
                  {
                    AllVirtual = TargetInfo::ReadAllVirtual(
                                   g_Target,
                                   g_Process,
                                   v17[10],
                                   *((void **)this + 6551),
                                   8u,
                                   0);
                    if ( AllVirtual )
                    {
                      VerbOut(
                        L"KernelTriageDumpTargetInfo::GetWdfTriageInformation::           ==> Unable to read WdfDeviceTria"
                         "geInfo structure");
                    }
                    else
                    {
                      AllVirtual = TargetInfo::ReadAllVirtual(
                                     g_Target,
                                     g_Process,
                                     v17[11],
                                     *((void **)this + 6552),
                                     8u,
                                     0);
                      if ( !AllVirtual )
                      {
                        *((_BYTE *)this + 52424) = 1;
                        return AllVirtual;
                      }
                      VerbOut(
                        L"KernelTriageDumpTargetInfo::GetWdfTriageInformation::           ==> Unable to read WdfIrpTriageInfo structure");
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    else
    {
      VerbOut(L"KernelTriageDumpTargetInfo::GetWdfTriageInformation::Unable to allocate memory\n");
    }
LABEL_36:
    if ( AllVirtual )
      *((_BYTE *)this + 52424) = 0;
    return AllVirtual;
  }
  VerbOut(L"KernelTriageDumpTargetInfo::GetWdfTriageInformation::           ==> WDF triage info major version mismatch\n");
  return AllVirtual;
}

```

## disassembly

```asm
0x18022e688  push    rbp
0x18022e68a  push    rbx
0x18022e68b  push    rsi
0x18022e68c  push    rdi
0x18022e68d  push    r12
0x18022e68f  push    r14
0x18022e691  push    r15
0x18022e693  lea     rbp, [rsp-27h]
0x18022e698  sub     rsp, 90h
0x18022e69f  cmp     byte ptr [rcx+0CCC8h], 1
0x18022e6a6  mov     rbx, rdx
0x18022e6a9  mov     rdi, rcx
0x18022e6ac  jnz     short loc_18022E6B5
0x18022e6ae  xor     eax, eax
0x18022e6b0  jmp     loc_18022EB46
0x18022e6b5  mov     esi, 60h ; '`'
0x18022e6ba  lea     rcx, [rbp+57h+var_90]; void *
0x18022e6be  mov     r8d, esi; Size
0x18022e6c1  xor     edx, edx; Val
0x18022e6c3  call    memset
0x18022e6c8  mov     rdx, cs:?g_Process@@3PEAVProcessInfo@@EA; struct ProcessInfo *
0x18022e6cf  lea     r9, [rbp+57h+var_90]; void *
0x18022e6d3  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; this
0x18022e6da  xor     r14d, r14d
0x18022e6dd  mov     [rsp+0C0h+var_98], r14d; unsigned int
0x18022e6e2  mov     r8, rbx; unsigned __int64
0x18022e6e5  mov     [rsp+0C0h+var_A0], esi; unsigned int
0x18022e6e9  call    ?ReadAllVirtual@TargetInfo@@QEAAJPEAVProcessInfo@@_KPEAXKK@Z; TargetInfo::ReadAllVirtual(ProcessInfo *,unsigned __int64,void *,ulong,ulong)
0x18022e6ee  mov     ebx, eax
0x18022e6f0  test    eax, eax
0x18022e6f2  jz      short loc_18022E700
0x18022e6f4  lea     rcx, aKerneltriagedu_409; "KernelTriageDumpTargetInfo::GetWdfTriag"...
0x18022e6fb  jmp     loc_18022EB34
0x18022e700  cmp     [rbp+57h+var_88], 1
0x18022e704  jz      short loc_18022E717
0x18022e706  lea     rcx, aKerneltriagedu_202; "KernelTriageDumpTargetInfo::GetWdfTriag"...
0x18022e70d  call    ?VerbOut@@YAXPEBGZZ; VerbOut(ushort const *,...)
0x18022e712  jmp     loc_18022EB44
0x18022e717  mov     eax, [rbp+57h+var_90]
0x18022e71a  mov     [rdi+0CC68h], eax
0x18022e720  mov     eax, [rbp+57h+var_8C]
0x18022e723  mov     [rdi+0CC6Ch], eax
0x18022e729  mov     eax, [rbp+57h+var_84]
0x18022e72c  mov     [rdi+0CC74h], eax
0x18022e732  mov     dword ptr [rdi+0CC70h], 1
0x18022e73c  call    cs:__imp_GetProcessHeap
0x18022e743  nop     dword ptr [rax+rax+00h]
0x18022e748  mov     esi, 1Ch
0x18022e74d  mov     rcx, rax; hHeap
0x18022e750  mov     r8d, esi; dwBytes
0x18022e753  lea     r15d, [rsi-14h]
0x18022e757  mov     edx, r15d; dwFlags
0x18022e75a  call    cs:__imp_HeapAlloc
0x18022e761  nop     dword ptr [rax+rax+00h]
0x18022e766  mov     [rdi+0CC80h], rax
0x18022e76d  call    cs:__imp_GetProcessHeap
0x18022e774  nop     dword ptr [rax+rax+00h]
0x18022e779  lea     r8d, [rsi-8]; dwBytes
0x18022e77d  mov     edx, r15d; dwFlags
0x18022e780  mov     rcx, rax; hHeap
0x18022e783  call    cs:__imp_HeapAlloc
0x18022e78a  nop     dword ptr [rax+rax+00h]
0x18022e78f  mov     [rdi+0CC88h], rax
0x18022e796  call    cs:__imp_GetProcessHeap
0x18022e79d  nop     dword ptr [rax+rax+00h]
0x18022e7a2  lea     r12d, [rsi-10h]
0x18022e7a6  mov     edx, r15d; dwFlags
0x18022e7a9  mov     rcx, rax; hHeap
0x18022e7ac  mov     r8d, r12d; dwBytes
0x18022e7af  call    cs:__imp_HeapAlloc
0x18022e7b6  nop     dword ptr [rax+rax+00h]
0x18022e7bb  mov     [rdi+0CC90h], rax
0x18022e7c2  call    cs:__imp_GetProcessHeap
0x18022e7c9  nop     dword ptr [rax+rax+00h]
0x18022e7ce  mov     r8d, esi; dwBytes
0x18022e7d1  mov     edx, r15d; dwFlags
0x18022e7d4  mov     rcx, rax; hHeap
0x18022e7d7  call    cs:__imp_HeapAlloc
0x18022e7de  nop     dword ptr [rax+rax+00h]
0x18022e7e3  mov     [rdi+0CC98h], rax
0x18022e7ea  call    cs:__imp_GetProcessHeap
0x18022e7f1  nop     dword ptr [rax+rax+00h]
0x18022e7f6  mov     r8d, r12d; dwBytes
0x18022e7f9  mov     edx, r15d; dwFlags
0x18022e7fc  mov     rcx, rax; hHeap
0x18022e7ff  call    cs:__imp_HeapAlloc
0x18022e806  nop     dword ptr [rax+rax+00h]
0x18022e80b  mov     [rdi+0CCA0h], rax
0x18022e812  call    cs:__imp_GetProcessHeap
0x18022e819  nop     dword ptr [rax+rax+00h]
0x18022e81e  lea     r8d, [rsi-0Ch]; dwBytes
0x18022e822  mov     edx, r15d; dwFlags
0x18022e825  mov     rcx, rax; hHeap
0x18022e828  call    cs:__imp_HeapAlloc
0x18022e82f  nop     dword ptr [rax+rax+00h]
0x18022e834  mov     [rdi+0CCA8h], rax
0x18022e83b  call    cs:__imp_GetProcessHeap
0x18022e842  nop     dword ptr [rax+rax+00h]
0x18022e847  mov     r8d, esi; dwBytes
0x18022e84a  mov     edx, r15d; dwFlags
0x18022e84d  mov     rcx, rax; hHeap
0x18022e850  call    cs:__imp_HeapAlloc
0x18022e857  nop     dword ptr [rax+rax+00h]
0x18022e85c  mov     [rdi+0CCB0h], rax
0x18022e863  call    cs:__imp_GetProcessHeap
0x18022e86a  nop     dword ptr [rax+rax+00h]
0x18022e86f  mov     r8d, r15d; dwBytes
0x18022e872  mov     edx, r15d; dwFlags
0x18022e875  mov     rcx, rax; hHeap
0x18022e878  call    cs:__imp_HeapAlloc
0x18022e87f  nop     dword ptr [rax+rax+00h]
0x18022e884  mov     [rdi+0CCB8h], rax
0x18022e88b  call    cs:__imp_GetProcessHeap
0x18022e892  nop     dword ptr [rax+rax+00h]
0x18022e897  mov     r8d, r15d; dwBytes
0x18022e89a  mov     edx, r15d; dwFlags
0x18022e89d  mov     rcx, rax; hHeap
0x18022e8a0  call    cs:__imp_HeapAlloc
0x18022e8a7  nop     dword ptr [rax+rax+00h]
0x18022e8ac  mov     r9, [rdi+0CC80h]; void *
0x18022e8b3  mov     [rdi+0CCC0h], rax
0x18022e8ba  test    r9, r9
0x18022e8bd  jz      loc_18022EB2D
0x18022e8c3  cmp     [rdi+0CC88h], r14
0x18022e8ca  jz      loc_18022EB2D
0x18022e8d0  cmp     [rdi+0CC90h], r14
0x18022e8d7  jz      loc_18022EB2D
0x18022e8dd  cmp     [rdi+0CC98h], r14
0x18022e8e4  jz      loc_18022EB2D
0x18022e8ea  cmp     [rdi+0CCA0h], r14
0x18022e8f1  jz      loc_18022EB2D
0x18022e8f7  cmp     [rdi+0CCA8h], r14
0x18022e8fe  jz      loc_18022EB2D
0x18022e904  cmp     [rdi+0CCB0h], r14
0x18022e90b  jz      loc_18022EB2D
0x18022e911  cmp     [rdi+0CCB8h], r14
0x18022e918  jz      loc_18022EB2D
0x18022e91e  test    rax, rax
0x18022e921  jz      loc_18022EB2D
0x18022e927  mov     r8, [rbp+57h+var_78]; unsigned __int64
0x18022e92b  mov     rdx, cs:?g_Process@@3PEAVProcessInfo@@EA; struct ProcessInfo *
0x18022e932  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; this
0x18022e939  mov     [rsp+0C0h+var_98], r14d; unsigned int
0x18022e93e  mov     [rsp+0C0h+var_A0], esi; unsigned int
0x18022e942  call    ?ReadAllVirtual@TargetInfo@@QEAAJPEAVProcessInfo@@_KPEAXKK@Z; TargetInfo::ReadAllVirtual(ProcessInfo *,unsigned __int64,void *,ulong,ulong)
0x18022e947  mov     ebx, eax
0x18022e949  test    eax, eax
0x18022e94b  jz      short loc_18022E959
0x18022e94d  lea     rcx, aKerneltriagedu_282; "KernelTriageDumpTargetInfo::GetWdfTriag"...
0x18022e954  jmp     loc_18022EB34
0x18022e959  mov     r9, [rdi+0CC88h]; void *
0x18022e960  mov     r8, [rbp+57h+var_70]; unsigned __int64
0x18022e964  mov     rdx, cs:?g_Process@@3PEAVProcessInfo@@EA; struct ProcessInfo *
0x18022e96b  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; this
0x18022e972  mov     [rsp+0C0h+var_98], r14d; unsigned int
0x18022e977  mov     [rsp+0C0h+var_A0], 14h; unsigned int
0x18022e97f  call    ?ReadAllVirtual@TargetInfo@@QEAAJPEAVProcessInfo@@_KPEAXKK@Z; TargetInfo::ReadAllVirtual(ProcessInfo *,unsigned __int64,void *,ulong,ulong)
0x18022e984  mov     ebx, eax
0x18022e986  test    eax, eax
0x18022e988  jz      short loc_18022E996
0x18022e98a  lea     rcx, aKerneltriagedu_434; "KernelTriageDumpTargetInfo::GetWdfTriag"...
0x18022e991  jmp     loc_18022EB34
0x18022e996  mov     r9, [rdi+0CC90h]; void *
0x18022e99d  mov     r8, [rbp+57h+var_68]; unsigned __int64
0x18022e9a1  mov     rdx, cs:?g_Process@@3PEAVProcessInfo@@EA; struct ProcessInfo *
0x18022e9a8  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; this
0x18022e9af  mov     [rsp+0C0h+var_98], r14d; unsigned int
0x18022e9b4  mov     [rsp+0C0h+var_A0], r12d; unsigned int
0x18022e9b9  call    ?ReadAllVirtual@TargetInfo@@QEAAJPEAVProcessInfo@@_KPEAXKK@Z; TargetInfo::ReadAllVirtual(ProcessInfo *,unsigned __int64,void *,ulong,ulong)
0x18022e9be  mov     ebx, eax
0x18022e9c0  test    eax, eax
0x18022e9c2  jz      short loc_18022E9D0
0x18022e9c4  lea     rcx, aKerneltriagedu_252; "KernelTriageDumpTargetInfo::GetWdfTriag"...
0x18022e9cb  jmp     loc_18022EB34
0x18022e9d0  mov     r9, [rdi+0CC98h]; void *
0x18022e9d7  mov     r8, [rbp+57h+var_60]; unsigned __int64
0x18022e9db  mov     rdx, cs:?g_Process@@3PEAVProcessInfo@@EA; struct ProcessInfo *
0x18022e9e2  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; this
0x18022e9e9  mov     [rsp+0C0h+var_98], r14d; unsigned int
0x18022e9ee  mov     [rsp+0C0h+var_A0], esi; unsigned int
0x18022e9f2  call    ?ReadAllVirtual@TargetInfo@@QEAAJPEAVProcessInfo@@_KPEAXKK@Z; TargetInfo::ReadAllVirtual(ProcessInfo *,unsigned __int64,void *,ulong,ulong)
0x18022e9f7  mov     ebx, eax
0x18022e9f9  test    eax, eax
0x18022e9fb  jz      short loc_18022EA09
0x18022e9fd  lea     rcx, aKerneltriagedu_185; "KernelTriageDumpTargetInfo::GetWdfTriag"...
0x18022ea04  jmp     loc_18022EB34
0x18022ea09  mov     r9, [rdi+0CCA0h]; void *
0x18022ea10  mov     r8, [rbp+57h+var_58]; unsigned __int64
0x18022ea14  mov     rdx, cs:?g_Process@@3PEAVProcessInfo@@EA; struct ProcessInfo *
0x18022ea1b  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; this
0x18022ea22  mov     [rsp+0C0h+var_98], r14d; unsigned int
0x18022ea27  mov     [rsp+0C0h+var_A0], r12d; unsigned int
0x18022ea2c  call    ?ReadAllVirtual@TargetInfo@@QEAAJPEAVProcessInfo@@_KPEAXKK@Z; TargetInfo::ReadAllVirtual(ProcessInfo *,unsigned __int64,void *,ulong,ulong)
0x18022ea31  mov     ebx, eax
0x18022ea33  test    eax, eax
0x18022ea35  jz      short loc_18022EA43
0x18022ea37  lea     rcx, aKerneltriagedu_364; "KernelTriageDumpTargetInfo::GetWdfTriag"...
0x18022ea3e  jmp     loc_18022EB34
0x18022ea43  mov     r9, [rdi+0CCA8h]; void *
0x18022ea4a  mov     r8, [rbp+57h+var_50]; unsigned __int64
0x18022ea4e  mov     rdx, cs:?g_Process@@3PEAVProcessInfo@@EA; struct ProcessInfo *
0x18022ea55  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; this
0x18022ea5c  mov     [rsp+0C0h+var_98], r14d; unsigned int
0x18022ea61  mov     [rsp+0C0h+var_A0], 10h; unsigned int
0x18022ea69  call    ?ReadAllVirtual@TargetInfo@@QEAAJPEAVProcessInfo@@_KPEAXKK@Z; TargetInfo::ReadAllVirtual(ProcessInfo *,unsigned __int64,void *,ulong,ulong)
0x18022ea6e  mov     ebx, eax
0x18022ea70  test    eax, eax
0x18022ea72  jz      short loc_18022EA80
0x18022ea74  lea     rcx, aKerneltriagedu_157; "KernelTriageDumpTargetInfo::GetWdfTriag"...
0x18022ea7b  jmp     loc_18022EB34
0x18022ea80  mov     r9, [rdi+0CCB0h]; void *
0x18022ea87  mov     r8, [rbp+57h+var_48]; unsigned __int64
0x18022ea8b  mov     rdx, cs:?g_Process@@3PEAVProcessInfo@@EA; struct ProcessInfo *
0x18022ea92  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; this
0x18022ea99  mov     [rsp+0C0h+var_98], r14d; unsigned int
0x18022ea9e  mov     [rsp+0C0h+var_A0], esi; unsigned int
0x18022eaa2  call    ?ReadAllVirtual@TargetInfo@@QEAAJPEAVProcessInfo@@_KPEAXKK@Z; TargetInfo::ReadAllVirtual(ProcessInfo *,unsigned __int64,void *,ulong,ulong)
0x18022eaa7  mov     ebx, eax
0x18022eaa9  test    eax, eax
0x18022eaab  jz      short loc_18022EAB6
0x18022eaad  lea     rcx, aKerneltriagedu_84; "KernelTriageDumpTargetInfo::GetWdfTriag"...
0x18022eab4  jmp     short loc_18022EB34
0x18022eab6  mov     r9, [rdi+0CCB8h]; void *
0x18022eabd  mov     r8, [rbp+57h+var_40]; unsigned __int64
0x18022eac1  mov     rdx, cs:?g_Process@@3PEAVProcessInfo@@EA; struct ProcessInfo *
0x18022eac8  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; this
0x18022eacf  mov     [rsp+0C0h+var_98], r14d; unsigned int
0x18022ead4  mov     [rsp+0C0h+var_A0], r15d; unsigned int
0x18022ead9  call    ?ReadAllVirtual@TargetInfo@@QEAAJPEAVProcessInfo@@_KPEAXKK@Z; TargetInfo::ReadAllVirtual(ProcessInfo *,unsigned __int64,void *,ulong,ulong)
0x18022eade  mov     ebx, eax
0x18022eae0  test    eax, eax
0x18022eae2  jz      short loc_18022EAED
0x18022eae4  lea     rcx, aKerneltriagedu_137; "KernelTriageDumpTargetInfo::GetWdfTriag"...
0x18022eaeb  jmp     short loc_18022EB34
0x18022eaed  mov     r9, [rdi+0CCC0h]; void *
0x18022eaf4  mov     r8, [rbp+57h+var_38]; unsigned __int64
0x18022eaf8  mov     rdx, cs:?g_Process@@3PEAVProcessInfo@@EA; struct ProcessInfo *
0x18022eaff  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; this
0x18022eb06  mov     [rsp+0C0h+var_98], r14d; unsigned int
0x18022eb0b  mov     [rsp+0C0h+var_A0], r15d; unsigned int
0x18022eb10  call    ?ReadAllVirtual@TargetInfo@@QEAAJPEAVProcessInfo@@_KPEAXKK@Z; TargetInfo::ReadAllVirtual(ProcessInfo *,unsigned __int64,void *,ulong,ulong)
0x18022eb15  mov     ebx, eax
0x18022eb17  test    eax, eax
0x18022eb19  jz      short loc_18022EB24
0x18022eb1b  lea     rcx, aKerneltriagedu_179; "KernelTriageDumpTargetInfo::GetWdfTriag"...
0x18022eb22  jmp     short loc_18022EB34
0x18022eb24  mov     byte ptr [rdi+0CCC8h], 1
0x18022eb2b  jmp     short loc_18022EB44
0x18022eb2d  lea     rcx, aKerneltriagedu_46; "KernelTriageDumpTargetInfo::GetWdfTriag"...
0x18022eb34  call    ?VerbOut@@YAXPEBGZZ; VerbOut(ushort const *,...)
0x18022eb39  test    ebx, ebx
0x18022eb3b  jz      short loc_18022EB44
0x18022eb3d  mov     [rdi+0CCC8h], r14b
0x18022eb44  mov     eax, ebx
0x18022eb46  add     rsp, 90h
0x18022eb4d  pop     r15
0x18022eb4f  pop     r14
0x18022eb51  pop     r12
0x18022eb53  pop     rdi
0x18022eb54  pop     rsi
0x18022eb55  pop     rbx
0x18022eb56  pop     rbp
0x18022eb57  retn
```
