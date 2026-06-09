# CKsProxy::AccessDeniedWaitThread(CKsProxy *)

- ea: `0x10008640`
- end: `0x100087b7`
- name: `?AccessDeniedWaitThread@CKsProxy@@SGKPAV1@@Z`
- size: `375`
- prototype: `ULONG __stdcall(HANDLE *Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x10006415`
- `0x10008640`
- `0x1000f598`
- `0x1002d510`
- `0x10030c17`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x10008658`
- `KERNEL32!WaitForSingleObjectEx` at `0x1000875f`
- `KERNEL32!WaitForSingleObjectEx` at `0x10008658`
- `KERNEL32!WaitForSingleObjectEx` at `0x1000875f`
- `KERNEL32!LeaveCriticalSection` at `0x1000873c`
- `KERNEL32!LeaveCriticalSection` at `0x10008787`
- `KERNEL32!LeaveCriticalSection` at `0x1000873c`
- `KERNEL32!LeaveCriticalSection` at `0x10008787`
- `KERNEL32!EnterCriticalSection` at `0x1000866d`
- `KERNEL32!EnterCriticalSection` at `0x1000866d`

## pseudocode

```c
ULONG __stdcall CKsProxy::AccessDeniedWaitThread(HANDLE *Parameter)
{
  HANDLE *v1; // edi
  struct _RTL_CRITICAL_SECTION *v2; // ebx
  HANDLE v3; // ecx
  _DWORD *v4; // ebx
  int v5; // edi
  int v6; // ecx
  _DWORD **v7; // ecx
  int v9; // [esp+14h] [ebp-8h] BYREF
  int v10; // [esp+18h] [ebp-4h] BYREF

  v1 = Parameter;
  if ( WaitForSingleObjectEx(Parameter[95], 0xFFFFFFFF, 0) )
  {
LABEL_17:
    CBaseFilter::NotifyEvent((CBaseFilter *)v1, 3, -2147024891, 0);
  }
  else
  {
    v2 = (struct _RTL_CRITICAL_SECTION *)(Parameter + 61);
    while ( 1 )
    {
      EnterCriticalSection(v2);
      if ( v1[60] )
        break;
      v3 = v1[94];
      v10 = -2147024891;
      if ( v3 )
        v10 = (*(int (__thiscall **)(_DWORD, HANDLE))(*(_DWORD *)v3 + 24))(*(_DWORD *)(*(_DWORD *)v3 + 24), v3);
      v4 = v1[43];
      if ( v4 )
      {
        v5 = v10;
        do
        {
          v6 = v4[2];
          v4 = (_DWORD *)v4[1];
          if ( *(_DWORD *)(v6 + 24) )
          {
            v10 = v6 + 12;
            if ( (*(int (__thiscall **)(_DWORD, int, int *))(*(_DWORD *)(v6 + 12) + 36))(
                   *(_DWORD *)(*(_DWORD *)(v6 + 12) + 36),
                   v6 + 12,
                   &v9) >= 0
              && v9 == 1 )
            {
              v7 = (_DWORD **)v10;
              v10 = 0;
              if ( ((int (__thiscall *)(_DWORD, _DWORD **, GUID *, int *))**v7)(
                     **v7,
                     v7,
                     &_GUID_7bb38260_d19c_11d2_b38a_00a0c95ec22e,
                     &v10) >= 0 )
                (*(void (__thiscall **)(_DWORD, int, _DWORD, int))(*(_DWORD *)v10 + 64))(
                  *(_DWORD *)(*(_DWORD *)v10 + 64),
                  v10,
                  0,
                  v5);
              wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(&v10);
            }
          }
        }
        while ( v4 );
        v1 = Parameter;
      }
      v2 = (struct _RTL_CRITICAL_SECTION *)(v1 + 61);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v1 + 61));
      (*((void (__thiscall **)(_DWORD, HANDLE *))v1[3] + 4))(*((_DWORD *)v1[3] + 4), v1 + 3);
      if ( WaitForSingleObjectEx(v1[95], 0xFFFFFFFF, 0) )
        goto LABEL_17;
    }
    LeaveCriticalSection(v2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_S(
        0xDu,
        &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids,
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (const unsigned __int16 *)v1[15]);
  }
  return 0;
}

```

## disassembly

```asm
0x10008640  mov     edi, edi
0x10008642  push    ebp
0x10008643  mov     ebp, esp
0x10008645  sub     esp, 10h
0x10008648  push    ebx
0x10008649  push    esi
0x1000864a  push    edi
0x1000864b  mov     edi, [ebp+Parameter]
0x1000864e  push    0; bAlertable
0x10008650  push    0FFFFFFFFh; dwMilliseconds
0x10008652  push    dword ptr [edi+17Ch]; hHandle
0x10008658  call    ds:__imp__WaitForSingleObjectEx@12; WaitForSingleObjectEx(x,x,x)
0x1000865e  test    eax, eax
0x10008660  jnz     loc_1000876D
0x10008666  lea     ebx, [edi+0F4h]
0x1000866c  push    ebx; lpCriticalSection
0x1000866d  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10008673  cmp     dword ptr [edi+0F0h], 0
0x1000867a  jnz     loc_10008786
0x10008680  mov     ecx, [edi+178h]
0x10008686  mov     [ebp+var_4], 80070005h
0x1000868d  test    ecx, ecx
0x1000868f  jz      short loc_100086A4
0x10008691  mov     eax, [ecx]
0x10008693  push    ecx
0x10008694  mov     esi, [eax+18h]
0x10008697  mov     ecx, esi; this
0x10008699  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000869f  call    esi
0x100086a1  mov     [ebp+var_4], eax
0x100086a4  mov     ebx, [edi+0ACh]
0x100086aa  test    ebx, ebx
0x100086ac  jz      loc_10008735
0x100086b2  mov     edi, [ebp+var_4]
0x100086b5  mov     ecx, [ebx+8]
0x100086b8  mov     ebx, [ebx+4]
0x100086bb  mov     [ebp+var_C], ebx
0x100086be  cmp     dword ptr [ecx+18h], 0
0x100086c2  jz      short loc_1000872C
0x100086c4  add     ecx, 0Ch
0x100086c7  mov     [ebp+var_4], ecx
0x100086ca  mov     eax, [ecx]
0x100086cc  mov     esi, [eax+24h]
0x100086cf  lea     eax, [ebp+var_8]
0x100086d2  push    eax
0x100086d3  push    ecx
0x100086d4  mov     ecx, esi; this
0x100086d6  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100086dc  call    esi
0x100086de  test    eax, eax
0x100086e0  js      short loc_1000872C
0x100086e2  cmp     [ebp+var_8], 1
0x100086e6  jnz     short loc_1000872C
0x100086e8  mov     ecx, [ebp+var_4]
0x100086eb  mov     [ebp+var_4], 0
0x100086f2  mov     eax, [ecx]
0x100086f4  mov     esi, [eax]
0x100086f6  lea     eax, [ebp+var_4]
0x100086f9  push    eax
0x100086fa  push    offset __GUID_7bb38260_d19c_11d2_b38a_00a0c95ec22e
0x100086ff  push    ecx
0x10008700  mov     ecx, esi; this
0x10008702  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10008708  call    esi
0x1000870a  test    eax, eax
0x1000870c  js      short loc_10008724
0x1000870e  mov     eax, [ebp+var_4]
0x10008711  push    edi
0x10008712  push    0
0x10008714  push    eax
0x10008715  mov     ecx, [eax]
0x10008717  mov     esi, [ecx+40h]
0x1000871a  mov     ecx, esi; this
0x1000871c  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10008722  call    esi
0x10008724  lea     ecx, [ebp+var_4]
0x10008727  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x1000872c  cmp     [ebp+var_C], 0
0x10008730  jnz     short loc_100086B5
0x10008732  mov     edi, [ebp+Parameter]
0x10008735  lea     ebx, [edi+0F4h]
0x1000873b  push    ebx; lpCriticalSection
0x1000873c  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10008742  lea     eax, [edi+0Ch]
0x10008745  mov     ecx, [eax]
0x10008747  push    eax
0x10008748  mov     esi, [ecx+10h]
0x1000874b  mov     ecx, esi; this
0x1000874d  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10008753  call    esi
0x10008755  push    0; bAlertable
0x10008757  push    0FFFFFFFFh; dwMilliseconds
0x10008759  push    dword ptr [edi+17Ch]; hHandle
0x1000875f  call    ds:__imp__WaitForSingleObjectEx@12; WaitForSingleObjectEx(x,x,x)
0x10008765  test    eax, eax
0x10008767  jz      loc_1000866C
0x1000876d  push    0; int
0x1000876f  push    80070005h; int
0x10008774  push    3; int
0x10008776  mov     ecx, edi; this
0x10008778  call    ?NotifyEvent@CBaseFilter@@QAEJJJJ@Z; CBaseFilter::NotifyEvent(long,long,long)
0x1000877d  pop     edi
0x1000877e  pop     esi
0x1000877f  xor     eax, eax
0x10008781  pop     ebx
0x10008782  leave
0x10008783  retn    4
0x10008786  push    ebx; lpCriticalSection
0x10008787  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000878d  mov     eax, _WPP_GLOBAL_Control
0x10008792  cmp     eax, offset _WPP_GLOBAL_Control
0x10008797  jz      short loc_1000877D
0x10008799  cmp     byte ptr [eax+19h], 2
0x1000879d  jb      short loc_1000877D
0x1000879f  push    dword ptr [edi+3Ch]; int
0x100087a2  mov     edx, offset _WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids; MessageGuid
0x100087a7  push    dword ptr [eax+14h]
0x100087aa  push    dword ptr [eax+10h]; LoggerHandle
0x100087ad  push    0Dh
0x100087af  pop     ecx; MessageNumber
0x100087b0  call    _WPP_SF_S@20; WPP_SF_S(x,x,x,x,x)
0x100087b5  jmp     short loc_1000877D
```
