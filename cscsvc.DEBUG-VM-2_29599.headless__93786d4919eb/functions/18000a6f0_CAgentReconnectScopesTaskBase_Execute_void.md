# CAgentReconnectScopesTaskBase::Execute(void)

- ea: `0x18000a6f0`
- end: `0x18000adb5`
- name: `?Execute@CAgentReconnectScopesTaskBase@@UEAAXXZ`
- size: `1733`
- prototype: `void __fastcall(CAgentReconnectScopesTaskBase *__hidden this)`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800068b0`
- `0x18000a6c8`
- `0x18000a6f0`
- `0x18000adc0`
- `0x18000b2fc`
- `0x18000b91c`
- `0x18001a340`
- `0x18001b4e0`
- `0x18001be00`
- `0x18002a478`
- `0x18002f10c`
- `0x180036394`
- `0x180039610`
- `0x18003c488`
- `0x18003c5ec`
- `0x18005fa04`
- `0x180087614`
- `0x180089010`

## import_xrefs

- `ntdll!RtlpEnsureBufferSize` at `0x18000a7fa`
- `ntdll!RtlpEnsureBufferSize` at `0x18000a7fa`
- `ntdll!RtlFreeUnicodeString` at `0x18000ad89`
- `ntdll!RtlFreeUnicodeString` at `0x18000adaa`
- `ntdll!RtlFreeUnicodeString` at `0x18000ad89`
- `ntdll!RtlFreeUnicodeString` at `0x18000adaa`
- `ntdll!RtlInitUnicodeString` at `0x18000a7bf`
- `ntdll!RtlInitUnicodeString` at `0x18000a7bf`
- `ntdll!NtClose` at `0x18000aa24`
- `ntdll!NtClose` at `0x18000aa24`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa74`
- `KERNEL32!CompareStringW` at `0x18000ac95`
- `KERNEL32!CompareStringW` at `0x18000ac95`

## pseudocode

```c
void __fastcall CAgentReconnectScopesTaskBase::Execute(CAgentReconnectScopesTaskBase *this)
{
  int v2; // ecx
  USHORT Length; // r8
  unsigned __int16 v4; // dx
  SIZE_T v5; // rax
  int v6; // edi
  unsigned __int64 v7; // rdx
  int v8; // r8d
  CObjectMonitor *v9; // rcx
  PVOID ReservedForIMalloc; // r9
  int v11; // r9d
  int v12; // eax
  int v13; // esi
  WCHAR *v14; // rdx
  void *v15; // rbx
  HANDLE ProcessHeap; // rax
  CObjectMonitor *v17; // r10
  int v18; // r8d
  int v19; // ecx
  const unsigned __int16 *ConstBuffer; // rax
  __int64 v21; // r10
  const WCHAR *v22; // rax
  PCNZWCH lpString2; // rdx
  unsigned int v24; // eax
  __int64 v25; // r10
  __int64 v26; // r8
  const unsigned __int16 *v27; // rax
  __int64 v28; // r10
  const unsigned __int16 *v29; // rax
  __int64 v30; // r10
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v33[260]; // [rsp+60h] [rbp-A0h] BYREF
  int v34; // [rsp+268h] [rbp+168h]
  PUCHAR v35; // [rsp+270h] [rbp+170h]
  struct _RTL_BUFFER Buffer; // [rsp+278h] [rbp+178h] BYREF
  int v37; // [rsp+2A8h] [rbp+1A8h]
  LPVOID lpMem[2]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _WORD v39[260]; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v40; // [rsp+4C8h] [rbp+3C8h]
  _WORD *v41; // [rsp+4D0h] [rbp+3D0h]
  WCHAR *v42; // [rsp+4D8h] [rbp+3D8h]
  CObjectMonitor *v43; // [rsp+4E0h] [rbp+3E0h]
  __int64 v44; // [rsp+4E8h] [rbp+3E8h]
  __int64 v45; // [rsp+4F0h] [rbp+3F0h]

  if ( !(*(unsigned int (__fastcall **)(CAgentReconnectScopesTaskBase *))(*(_QWORD *)this + 80LL))(this) )
    return;
  EventDispatcherRcv_ItemReconnectBegin(v2);
  v34 = 34078720;
  v33[0] = 0;
  Buffer.Buffer = (PUCHAR)v33;
  Buffer.ReservedForIMalloc = 0;
  Buffer.StaticBuffer = (PUCHAR)v33;
  v37 = 0;
  v35 = (PUCHAR)v33;
  Buffer.Size = 520;
  Buffer.StaticSize = 520;
  *(_OWORD *)lpMem = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, &Class);
  Length = DestinationString.Length;
  v4 = 0;
  LOWORD(v34) = 0;
  v5 = DestinationString.Length + 2LL;
  if ( v5 > 0xFFFE )
  {
    v19 = -1073741562;
  }
  else
  {
    if ( v5 <= Buffer.Size )
    {
LABEL_6:
      v35 = Buffer.Buffer;
      memmove_0(&Buffer.Buffer[2 * ((unsigned __int64)v4 >> 1)], DestinationString.Buffer, Length);
      v6 = 0;
      v7 = (unsigned __int16)(DestinationString.Length + v34);
      LOWORD(v34) = v7;
      HIWORD(v34) = v7 + 2;
      *(_WORD *)&v35[2 * (v7 >> 1)] = 0;
LABEL_7:
      v8 = 3;
      *(_DWORD *)&DestinationString.Length = 3;
      UnicodeString.Buffer = (PWSTR)L"\\";
      *(_QWORD *)&UnicodeString.Length = 262146;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      {
        WPP_SF_qqD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          20,
          WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids,
          &Buffer.ReservedForIMalloc,
          &DestinationString,
          3);
        v8 = *(_DWORD *)&DestinationString.Length;
        v9 = WPP_GLOBAL_Control;
      }
      Buffer.ReservedForIMalloc = 0;
      ReservedForIMalloc = 0;
      if ( v8 == 3 )
      {
        v11 = 293;
      }
      else
      {
        v18 = v8 - 1;
        if ( v18 )
        {
          if ( v18 != 1 )
          {
            v13 = -1073741811;
            goto LABEL_12;
          }
          v11 = 549;
        }
        else
        {
          v11 = 1061;
        }
      }
      v12 = CscDriverOpenItemWithDispositionEx(&Buffer.ReservedForIMalloc, 0, &UnicodeString, v11, 1179785, 7u, 1u, 0);
      ReservedForIMalloc = Buffer.ReservedForIMalloc;
      v13 = v12;
      v9 = WPP_GLOBAL_Control;
LABEL_12:
      if ( v9 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 68) & 8) != 0 && *((_BYTE *)v9 + 65) >= 4u )
      {
        WPP_SF_qqD(
          *((_QWORD *)v9 + 7),
          21,
          WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids,
          &Buffer.ReservedForIMalloc,
          ReservedForIMalloc,
          v13);
        v9 = WPP_GLOBAL_Control;
      }
      if ( v13 < 0 )
      {
        if ( v9 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)v9 + 2), 10, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids, (unsigned int)v13);
        v6 = ResultFromNtStatus(v13);
      }
      else
      {
        lpMem[1] = 0;
        v37 = 0;
        if ( !lpMem[0] )
        {
          LODWORD(v9) = 2048;
          lpMem[0] = 0;
          if ( is_mul_ok(0x800u, 1u) )
            v6 = CscUtil_HeapAlloc(0x800u, 1, lpMem, ReservedForIMalloc);
          else
            v6 = -2147024362;
        }
      }
      if ( v6 >= 0 )
      {
        v14 = v39;
        v44 = 520;
        v9 = (CObjectMonitor *)v39;
        v42 = v39;
        v43 = (CObjectMonitor *)v39;
        v41 = v39;
        v45 = 520;
        v39[0] = 0;
        v40 = 34078720;
        if ( !*((_DWORD *)this + 28) )
        {
          while ( 1 )
          {
            while ( 1 )
            {
              if ( (unsigned int)CCscScopeEnum::_NextScope((CCscScopeEnum *)v33, (struct CCscScope *)v39) )
              {
LABEL_18:
                v9 = v43;
                v14 = v42;
                goto LABEL_19;
              }
              if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
              {
                ConstBuffer = CPath::_GetConstBuffer((CPath *)v39);
                WPP_SF_S(*(_QWORD *)(v21 + 16), 11, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids, ConstBuffer);
              }
              if ( !(unsigned int)CPath::IsEmpty((CPath *)v33) )
                break;
LABEL_40:
              if ( v17 != (CObjectMonitor *)&WPP_GLOBAL_Control )
              {
                if ( (*((_DWORD *)v17 + 7) & 0x400) != 0 )
                {
                  v27 = CPath::_GetConstBuffer((CPath *)v39);
                  WPP_SF_S(*(_QWORD *)(v28 + 16), 12, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids, v27);
                  v17 = WPP_GLOBAL_Control;
                }
                if ( v17 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_DWORD *)v17 + 7) & 0x400) != 0 )
                {
                  v29 = CPath::_GetConstBuffer((CPath *)v39);
                  WPP_SF_S(*(_QWORD *)(v30 + 16), 18, WPP_1b2e11bf501d36099a40201e41f6b5dd_Traceguids, v29);
                }
              }
              CCscScope::Maintain(v39, 0);
              if ( *((_DWORD *)this + 28) )
                goto LABEL_18;
            }
            CPath::_GetConstBuffer((CPath *)v33);
            v22 = CPath::_GetConstBuffer((CPath *)v39);
            if ( CompareStringW(0x7Fu, 1u, v22, -1, lpString2, -1) == 2 )
            {
              v17 = WPP_GLOBAL_Control;
              goto LABEL_40;
            }
            if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            {
              CPath::_GetConstBuffer((CPath *)v33);
              v24 = (unsigned int)CPath::_GetConstBuffer((CPath *)v39);
              WPP_SF_SS(
                *(_QWORD *)(v25 + 16),
                13,
                (unsigned int)WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids,
                v24,
                v26);
            }
          }
        }
LABEL_19:
        if ( v14 && v14 != (WCHAR *)v9 )
        {
          *(_QWORD *)&UnicodeString.Length = 0;
          UnicodeString.Buffer = v14;
          RtlFreeUnicodeString(&UnicodeString);
          v9 = v43;
        }
        if ( v9 )
          *(_WORD *)v9 = 0;
      }
      goto LABEL_26;
    }
    if ( RtlpEnsureBufferSize(0, &Buffer, DestinationString.Length + 2LL) >= 0 )
    {
      v4 = v34;
      Length = DestinationString.Length;
      goto LABEL_6;
    }
    v19 = -1073741801;
  }
  v6 = ResultFromNtStatus(v19);
  if ( v6 >= 0 )
    goto LABEL_7;
LABEL_26:
  EventDispatcherRcv_ItemReconnectEnd((int)v9);
  v15 = lpMem[0];
  if ( lpMem[0] )
  {
    ProcessHeap = GetProcessHeap();
    if ( ProcessHeap )
    {
      if ( !HeapFree(ProcessHeap, 0, v15) )
        ResultFromLastError();
    }
  }
  if ( Buffer.ReservedForIMalloc )
    NtClose(Buffer.ReservedForIMalloc);
  if ( Buffer.Buffer && Buffer.Buffer != Buffer.StaticBuffer )
  {
    *(_QWORD *)&UnicodeString.Length = 0;
    UnicodeString.Buffer = (PWSTR)Buffer.Buffer;
    RtlFreeUnicodeString(&UnicodeString);
  }
  if ( Buffer.StaticBuffer )
    *(_WORD *)Buffer.StaticBuffer = 0;
}

```

## disassembly

```asm
0x18000a6f0  push    rbp
0x18000a6f2  push    rbx
0x18000a6f3  lea     rbp, [rsp-448h]
0x18000a6fb  sub     rsp, 548h
0x18000a702  mov     rax, cs:__security_cookie
0x18000a709  xor     rax, rsp
0x18000a70c  mov     [rbp+450h+var_30], rax
0x18000a713  mov     rax, [rcx]
0x18000a716  mov     rbx, rcx
0x18000a719  mov     rax, [rax+50h]
0x18000a71d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a722  test    eax, eax
0x18000a724  jz      loc_18000AA5B
0x18000a72a  mov     [rsp+550h+var_18], r14
0x18000a732  mov     [rsp+550h+var_20], r15
0x18000a73a  mov     [rsp+550h+arg_10], rdi
0x18000a742  call    ?EventDispatcherRcv_ItemReconnectBegin@@YAJH@Z; EventDispatcherRcv_ItemReconnectBegin(int)
0x18000a747  xor     r14d, r14d
0x18000a74a  mov     [rbp+450h+var_2E8], 2080000h
0x18000a754  lea     rax, [rsp+550h+var_4F0]
0x18000a759  mov     [rsp+550h+var_4F0], r14w
0x18000a75f  mov     [rbp+450h+Buffer.Buffer], rax
0x18000a766  lea     rdx, Class; SourceString
0x18000a76d  lea     rax, [rsp+550h+var_4F0]
0x18000a772  mov     [rbp+450h+Buffer.ReservedForIMalloc], r14
0x18000a779  mov     [rbp+450h+Buffer.StaticBuffer], rax
0x18000a780  lea     rcx, [rsp+550h+DestinationString]; DestinationString
0x18000a785  lea     rax, [rsp+550h+var_4F0]
0x18000a78a  mov     [rbp+450h+var_2A8], r14d
0x18000a791  mov     r15d, 208h
0x18000a797  mov     [rbp+450h+var_2E0], rax
0x18000a79e  xorps   xmm0, xmm0
0x18000a7a1  mov     [rbp+450h+Buffer.Size], r15
0x18000a7a8  xorps   xmm1, xmm1
0x18000a7ab  mov     [rbp+450h+Buffer.StaticSize], r15
0x18000a7b2  movdqa  xmmword ptr [rbp+450h+lpMem], xmm0
0x18000a7ba  movups  xmmword ptr [rsp+550h+DestinationString.Length], xmm1
0x18000a7bf  call    cs:__imp_RtlInitUnicodeString
0x18000a7c5  movzx   r8d, [rsp+550h+DestinationString.Length]
0x18000a7cb  mov     edx, r14d
0x18000a7ce  mov     word ptr [rbp+450h+var_2E8], dx
0x18000a7d5  lea     rax, [r8+2]
0x18000a7d9  cmp     rax, 0FFFEh
0x18000a7df  ja      loc_18000AB62
0x18000a7e5  cmp     rax, [rbp+450h+Buffer.Size]
0x18000a7ec  jbe     short loc_18000A815
0x18000a7ee  mov     r8, rax; RequiredSize
0x18000a7f1  lea     rdx, [rbp+450h+Buffer]; Buffer
0x18000a7f8  xor     ecx, ecx; Flags
0x18000a7fa  call    cs:__imp_RtlpEnsureBufferSize
0x18000a800  test    eax, eax
0x18000a802  js      loc_18000AB6C
0x18000a808  movzx   edx, word ptr [rbp+450h+var_2E8]
0x18000a80f  movzx   r8d, [rsp+550h+DestinationString.Length]
0x18000a815  mov     rcx, [rbp+450h+Buffer.Buffer]
0x18000a81c  movzx   eax, dx
0x18000a81f  mov     rdx, [rsp+550h+DestinationString.Buffer]; Src
0x18000a824  shr     rax, 1
0x18000a827  mov     [rbp+450h+var_2E0], rcx
0x18000a82e  movzx   r8d, r8w; Size
0x18000a832  lea     rcx, [rcx+rax*2]; void *
0x18000a836  call    memmove_0
0x18000a83b  movzx   eax, word ptr [rbp+450h+var_2E8]
0x18000a842  mov     edi, r14d
0x18000a845  add     ax, [rsp+550h+DestinationString.Length]
0x18000a84a  movzx   edx, ax
0x18000a84d  mov     word ptr [rbp+450h+var_2E8], dx
0x18000a854  lea     eax, [rdx+2]
0x18000a857  shr     rdx, 1
0x18000a85a  mov     word ptr [rbp+450h+var_2E8+2], ax
0x18000a861  mov     rax, [rbp+450h+var_2E0]
0x18000a868  mov     [rax+rdx*2], r14w
0x18000a86d  mov     r8d, 3
0x18000a873  mov     [rsp+550h+arg_8], rsi
0x18000a87b  lea     rax, Src; "\\"
0x18000a882  mov     dword ptr [rsp+550h+DestinationString.Length], r8d
0x18000a887  mov     [rsp+550h+UnicodeString.Buffer], rax
0x18000a88c  mov     [rsp+550h+var_10], r12
0x18000a894  mov     qword ptr [rsp+550h+UnicodeString.Length], 40002h
0x18000a89d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8a4  lea     r12, WPP_GLOBAL_Control
0x18000a8ab  cmp     rcx, r12
0x18000a8ae  jz      short loc_18000A8BA
0x18000a8b0  test    byte ptr [rcx+44h], 8
0x18000a8b4  jnz     loc_18000AB76
0x18000a8ba  mov     [rbp+450h+Buffer.ReservedForIMalloc], r14
0x18000a8c1  mov     r9, r14
0x18000a8c4  cmp     r8d, 3
0x18000a8c8  jnz     loc_18000AB4C
0x18000a8ce  mov     r9d, 125h
0x18000a8d4  mov     [rsp+550h+var_518], r14d; int
0x18000a8d9  lea     r8, [rsp+550h+UnicodeString]
0x18000a8de  mov     [rsp+550h+var_520], 1; ULONG
0x18000a8e6  lea     rcx, [rbp+450h+Buffer.ReservedForIMalloc]; FileHandle
0x18000a8ed  mov     [rsp+550h+cchCount2], 7; ULONG
0x18000a8f5  xor     edx, edx
0x18000a8f7  mov     dword ptr [rsp+550h+lpString2], 120089h; int
0x18000a8ff  call    CscDriverOpenItemWithDispositionEx
0x18000a904  mov     r9, [rbp+450h+Buffer.ReservedForIMalloc]; void *
0x18000a90b  mov     esi, eax
0x18000a90d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a914  cmp     rcx, r12
0x18000a917  jnz     loc_18000AAE0
0x18000a91d  test    esi, esi
0x18000a91f  js      loc_18000ABD2
0x18000a925  mov     [rbp+450h+lpMem+8], r14
0x18000a92c  mov     [rbp+450h+var_2A8], r14d
0x18000a933  cmp     [rbp+450h+lpMem], r14
0x18000a93a  jz      loc_18000AB25
0x18000a940  mov     rsi, [rsp+550h+arg_8]
0x18000a948  test    edi, edi
0x18000a94a  js      loc_18000A9DE
0x18000a950  lea     rdx, [rbp+450h+var_290]
0x18000a957  mov     [rbp+450h+var_68], r15
0x18000a95e  lea     rcx, [rbp+450h+var_290]
0x18000a965  mov     [rbp+450h+var_78], rdx
0x18000a96c  lea     rax, [rbp+450h+var_290]
0x18000a973  mov     [rbp+450h+var_70], rcx
0x18000a97a  mov     [rbp+450h+var_80], rax
0x18000a981  mov     [rbp+450h+var_60], r15
0x18000a988  mov     [rbp+450h+var_290], r14w
0x18000a990  mov     [rbp+450h+var_88], 2080000h
0x18000a99a  cmp     [rbx+70h], r14d
0x18000a99e  jnz     short loc_18000A9C7
0x18000a9a0  lea     rdx, [rbp+450h+var_290]; struct CCscScope *
0x18000a9a7  lea     rcx, [rsp+550h+var_4F0]; this
0x18000a9ac  call    ?_NextScope@CCscScopeEnum@@AEAAJPEAVCCscScope@@@Z; CCscScopeEnum::_NextScope(CCscScope *)
0x18000a9b1  test    eax, eax
0x18000a9b3  jz      loc_18000AA98
0x18000a9b9  mov     rcx, [rbp+450h+var_70]
0x18000a9c0  mov     rdx, [rbp+450h+var_78]
0x18000a9c7  test    rdx, rdx
0x18000a9ca  jz      short loc_18000A9D5
0x18000a9cc  cmp     rdx, rcx
0x18000a9cf  jnz     loc_18000AD7A
0x18000a9d5  test    rcx, rcx
0x18000a9d8  jz      short loc_18000A9DE
0x18000a9da  mov     [rcx], r14w
0x18000a9de  mov     r12, [rsp+550h+var_10]
0x18000a9e6  jmp     short loc_18000A9F7
0x18000a9e8  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x18000a9ed  mov     edi, eax
0x18000a9ef  test    eax, eax
0x18000a9f1  jns     loc_18000A86D
0x18000a9f7  call    ?EventDispatcherRcv_ItemReconnectEnd@@YAJH@Z; EventDispatcherRcv_ItemReconnectEnd(int)
0x18000a9fc  mov     rbx, [rbp+450h+lpMem]
0x18000aa03  mov     r15, [rsp+550h+var_20]
0x18000aa0b  mov     rdi, [rsp+550h+arg_10]
0x18000aa13  test    rbx, rbx
0x18000aa16  jnz     short loc_18000AA74
0x18000aa18  mov     rcx, [rbp+450h+Buffer.ReservedForIMalloc]; Handle
0x18000aa1f  test    rcx, rcx
0x18000aa22  jz      short loc_18000AA2A
0x18000aa24  call    cs:__imp_NtClose
0x18000aa2a  mov     rax, [rbp+450h+Buffer.Buffer]
0x18000aa31  test    rax, rax
0x18000aa34  jz      short loc_18000AA43
0x18000aa36  cmp     rax, [rbp+450h+Buffer.StaticBuffer]
0x18000aa3d  jnz     loc_18000AD9B
0x18000aa43  mov     rcx, [rbp+450h+Buffer.StaticBuffer]
0x18000aa4a  test    rcx, rcx
0x18000aa4d  jz      short loc_18000AA53
0x18000aa4f  mov     [rcx], r14w
0x18000aa53  mov     r14, [rsp+550h+var_18]
0x18000aa5b  mov     rcx, [rbp+450h+var_30]
0x18000aa62  xor     rcx, rsp; StackCookie
0x18000aa65  call    __security_check_cookie
0x18000aa6a  add     rsp, 548h
0x18000aa71  pop     rbx
0x18000aa72  pop     rbp
0x18000aa73  retn
0x18000aa74  call    cs:__imp_GetProcessHeap
0x18000aa7a  test    rax, rax
0x18000aa7d  jz      short loc_18000AA18
0x18000aa7f  mov     r8, rbx; lpMem
0x18000aa82  xor     edx, edx; dwFlags
0x18000aa84  mov     rcx, rax; hHeap
0x18000aa87  call    cs:__imp_HeapFree
0x18000aa8d  test    eax, eax
0x18000aa8f  jnz     short loc_18000AA18
0x18000aa91  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18000aa96  jmp     short loc_18000AA18
0x18000aa98  mov     r10, cs:WPP_GLOBAL_Control
0x18000aa9f  cmp     r10, r12
0x18000aaa2  jnz     loc_18000AC1E
0x18000aaa8  lea     rcx, [rsp+550h+var_4F0]; this
0x18000aaad  call    ?IsEmpty@CPath@@QEAAHXZ; CPath::IsEmpty(void)
0x18000aab2  test    eax, eax
0x18000aab4  jz      loc_18000AC5C
0x18000aaba  cmp     r10, r12
0x18000aabd  jnz     loc_18000AD05
0x18000aac3  xor     edx, edx
0x18000aac5  lea     rcx, [rbp+450h+var_290]
0x18000aacc  call    ?Maintain@CCscScope@@QEAAJW4_CSC_SCOPE_MAINTAIN@@@Z; CCscScope::Maintain(_CSC_SCOPE_MAINTAIN)
0x18000aad1  cmp     [rbx+70h], r14d
0x18000aad5  jz      loc_18000A9A0
0x18000aadb  jmp     loc_18000A9B9
0x18000aae0  test    byte ptr [rcx+44h], 8
0x18000aae4  jz      loc_18000A91D
0x18000aaea  cmp     byte ptr [rcx+41h], 4
0x18000aaee  jb      loc_18000A91D
0x18000aaf4  mov     rcx, [rcx+38h]
0x18000aaf8  lea     r8, WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids
0x18000aaff  mov     [rsp+550h+cchCount2], esi
0x18000ab03  mov     edx, 15h
0x18000ab08  mov     [rsp+550h+lpString2], r9
0x18000ab0d  lea     r9, [rbp+450h+Buffer.ReservedForIMalloc]
0x18000ab14  call    WPP_SF_qqD
0x18000ab19  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab20  jmp     loc_18000A91D
0x18000ab25  mov     ecx, 800h
0x18000ab2a  mov     [rbp+450h+lpMem], r14
0x18000ab31  mov     eax, 1
0x18000ab36  mul     rcx
0x18000ab39  test    rdx, rdx
0x18000ab3c  jz      loc_18000AC03
0x18000ab42  mov     edi, 80070216h
0x18000ab47  jmp     loc_18000A940
0x18000ab4c  sub     r8d, 1
0x18000ab50  jz      short loc_18000ABC7
0x18000ab52  cmp     r8d, 1
0x18000ab56  jz      short loc_18000ABBC
0x18000ab58  mov     esi, 0C000000Dh
0x18000ab5d  jmp     loc_18000A914
0x18000ab62  mov     ecx, 0C0000106h; int
0x18000ab67  jmp     loc_18000A9E8
0x18000ab6c  mov     ecx, 0C0000017h
0x18000ab71  jmp     loc_18000A9E8
0x18000ab76  cmp     byte ptr [rcx+41h], 4
0x18000ab7a  jb      loc_18000A8BA
0x18000ab80  mov     rcx, [rcx+38h]
0x18000ab84  lea     rax, [rsp+550h+DestinationString]
0x18000ab89  mov     [rsp+550h+cchCount2], r8d
0x18000ab8e  lea     r9, [rbp+450h+Buffer.ReservedForIMalloc]
0x18000ab95  lea     r8, WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids
0x18000ab9c  mov     [rsp+550h+lpString2], rax
0x18000aba1  mov     edx, 14h
0x18000aba6  call    WPP_SF_qqD
0x18000abab  mov     r8d, dword ptr [rsp+550h+DestinationString.Length]
0x18000abb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abb7  jmp     loc_18000A8BA
0x18000abbc  mov     r9d, 225h
0x18000abc2  jmp     loc_18000A8D4
0x18000abc7  mov     r9d, 425h
0x18000abcd  jmp     loc_18000A8D4
0x18000abd2  cmp     rcx, r12
0x18000abd5  jz      short loc_18000ABF5
0x18000abd7  test    byte ptr [rcx+1Ch], 2
0x18000abdb  jz      short loc_18000ABF5
0x18000abdd  mov     rcx, [rcx+10h]
0x18000abe1  lea     r8, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids
0x18000abe8  mov     edx, 0Ah
0x18000abed  mov     r9d, esi
0x18000abf0  call    WPP_SF_d
0x18000abf5  mov     ecx, esi; int
0x18000abf7  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x18000abfc  mov     edi, eax
0x18000abfe  jmp     loc_18000A940
0x18000ac03  lea     r8, [rbp+450h+lpMem]; void **
0x18000ac0a  mov     edx, 1; int
0x18000ac0f  mov     rcx, rax; dwBytes
0x18000ac12  call    ?CscUtil_HeapAlloc@@YAJ_KHPEAPEAXPEAX@Z; CscUtil_HeapAlloc(unsigned __int64,int,void * *,void *)
0x18000ac17  mov     edi, eax
0x18000ac19  jmp     loc_18000A940
0x18000ac1e  test    dword ptr [r10+1Ch], 400h
0x18000ac26  jz      loc_18000AAA8
0x18000ac2c  lea     rcx, [rbp+450h+var_290]; this
0x18000ac33  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18000ac38  mov     rcx, [r10+10h]
0x18000ac3c  lea     r8, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids
0x18000ac43  mov     r9, rax
0x18000ac46  mov     edx, 0Bh
0x18000ac4b  call    WPP_SF_S
0x18000ac50  mov     r10, cs:WPP_GLOBAL_Control
0x18000ac57  jmp     loc_18000AAA8
0x18000ac5c  lea     rcx, [rsp+550h+var_4F0]; this
0x18000ac61  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18000ac66  lea     rcx, [rbp+450h+var_290]; this
0x18000ac6d  mov     rdx, rax
0x18000ac70  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18000ac75  mov     [rsp+550h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000ac7d  mov     r8, rax; lpString1
0x18000ac80  mov     [rsp+550h+lpString2], rdx; lpString2
0x18000ac85  mov     ecx, 7Fh; Locale
0x18000ac8a  mov     edx, 1; dwCmpFlags
0x18000ac8f  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000ac95  call    cs:__imp_CompareStringW
0x18000ac9b  cmp     eax, 2
0x18000ac9e  jz      short loc_18000ACF9
0x18000aca0  mov     r10, cs:WPP_GLOBAL_Control
0x18000aca7  cmp     r10, r12
0x18000acaa  jz      loc_18000A9A0
0x18000acb0  test    dword ptr [r10+1Ch], 400h
0x18000acb8  jz      loc_18000A9A0
0x18000acbe  lea     rcx, [rsp+550h+var_4F0]; this
0x18000acc3  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18000acc8  lea     rcx, [rbp+450h+var_290]; this
0x18000accf  mov     r8, rax
0x18000acd2  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18000acd7  mov     rcx, [r10+10h]
  ... truncated ...
```
