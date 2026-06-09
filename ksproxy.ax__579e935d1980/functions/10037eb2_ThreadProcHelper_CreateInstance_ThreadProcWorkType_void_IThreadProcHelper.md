# ThreadProcHelper::CreateInstance(ThreadProcWorkType,void *,IThreadProcHelper * *)

- ea: `0x10037eb2`
- end: `0x10037f95`
- name: `?CreateInstance@ThreadProcHelper@@SGJW4ThreadProcWorkType@@PAXPAPAUIThreadProcHelper@@@Z`
- size: `227`
- prototype: `static int __stdcall __high(enum ThreadProcWorkType, void *, struct IThreadProcHelper **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10037680`

## callees

- `0x100075ad`
- `0x1000f598`
- `0x1002d510`
- `0x10037eb2`
- `0x100380fb`
- `0x100387bc`
- `0x1003a6fd`
- `0x1003b5e4`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionEx` at `0x10037f07`
- `KERNEL32!InitializeCriticalSectionEx` at `0x10037f07`

## string_xrefs

- `0x10037f76`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\threadprochelper.cpp`

## pseudocode

```c
int __fastcall ThreadProcHelper::CreateInstance(int a1, void *a2, _DWORD *a3)
{
  int v3; // esi
  char *v4; // eax
  char *v5; // esi
  int v6; // ecx
  unsigned int v8; // [esp+0h] [ebp-14h]
  const char *v9; // [esp+4h] [ebp-10h]
  int v10; // [esp+8h] [ebp-Ch]
  _DWORD **v12; // [esp+10h] [ebp-4h] BYREF

  v12 = 0;
  if ( a3 )
  {
    *a3 = 0;
    v4 = (char *)operator new(0x44u);
    v5 = v4;
    if ( v4 )
    {
      memset(v4, 0, 0x44u);
      *(_DWORD *)v5 = &ThreadProcHelper::`vftable';
      InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v5 + 28), 0, 0);
      v5[52] = 0;
      *((_DWORD *)v5 + 14) = 0;
      *((_DWORD *)v5 + 15) = 2;
      *((_DWORD *)v5 + 16) = 1;
    }
    else
    {
      v5 = 0;
    }
    wil::com_ptr_t<ThreadProcHelper,wil::err_returncode_policy>::operator=(v5);
    if ( v12 )
    {
      v3 = ThreadProcHelper::InternalInitialize((int)v12, v6, a2);
      if ( v3 >= 0 )
      {
        v3 = ((int (__thiscall *)(_DWORD, _DWORD **, GUID *, _DWORD *))**v12)(
               **v12,
               v12,
               &_GUID_0beaa6cc_1392_4e3c_b0df_51b861bd6c6e,
               a3);
        if ( v3 >= 0 )
        {
          v3 = 0;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v3 = -2147024882;
    }
  }
  else
  {
    v3 = -2147467261;
  }
  wil::details::in1diag3::Return_Hr(
    (wil::details::in1diag3 *)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\threadprochelper.cpp",
    (void *)v3,
    v8,
    v9,
    v10);
LABEL_12:
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(&v12);
  return v3;
}

```

## disassembly

```asm
0x10037eb2  mov     edi, edi
0x10037eb4  push    ebp
0x10037eb5  mov     ebp, esp
0x10037eb7  push    ecx
0x10037eb8  push    ecx
0x10037eb9  push    ebx; int
0x10037eba  mov     ebx, [ebp+arg_0]
0x10037ebd  mov     [ebp+var_8], edx
0x10037ec0  mov     [ebp+var_4], 0
0x10037ec7  push    esi; char *
0x10037ec8  push    edi; unsigned int
0x10037ec9  test    ebx, ebx
0x10037ecb  jnz     short loc_10037ED9
0x10037ecd  mov     esi, 80004003h
0x10037ed2  push    11h
0x10037ed4  jmp     loc_10037F71
0x10037ed9  push    44h ; 'D'; Size
0x10037edb  mov     dword ptr [ebx], 0
0x10037ee1  call    ??2@YAPAXI@Z; operator new(uint)
0x10037ee6  mov     esi, eax
0x10037ee8  pop     ecx
0x10037ee9  test    esi, esi
0x10037eeb  jz      short loc_10037F24
0x10037eed  push    44h ; 'D'; Size
0x10037eef  xor     edi, edi
0x10037ef1  push    edi; Val
0x10037ef2  push    esi; void *
0x10037ef3  call    _memset
0x10037ef8  add     esp, 0Ch
0x10037efb  mov     dword ptr [esi], offset ??_7ThreadProcHelper@@6B@; const ThreadProcHelper::`vftable'
0x10037f01  lea     eax, [esi+1Ch]
0x10037f04  push    edi; Flags
0x10037f05  push    edi; dwSpinCount
0x10037f06  push    eax; lpCriticalSection
0x10037f07  call    ds:__imp__InitializeCriticalSectionEx@12; InitializeCriticalSectionEx(x,x,x)
0x10037f0d  mov     byte ptr [esi+34h], 0
0x10037f11  mov     [esi+38h], edi
0x10037f14  mov     dword ptr [esi+3Ch], 2
0x10037f1b  mov     dword ptr [esi+40h], 1
0x10037f22  jmp     short loc_10037F26
0x10037f24  xor     esi, esi
0x10037f26  push    esi
0x10037f27  lea     ecx, [ebp+var_4]
0x10037f2a  call    ??4?$com_ptr_t@VThreadProcHelper@@Uerr_returncode_policy@wil@@@wil@@QAEAAV01@PAVThreadProcHelper@@@Z; wil::com_ptr_t<ThreadProcHelper,wil::err_returncode_policy>::operator=(ThreadProcHelper *)
0x10037f2f  mov     edi, [ebp+var_4]
0x10037f32  test    edi, edi
0x10037f34  jnz     short loc_10037F3F
0x10037f36  mov     esi, 8007000Eh
0x10037f3b  push    15h
0x10037f3d  jmp     short loc_10037F71
0x10037f3f  push    [ebp+var_8]
0x10037f42  push    ecx
0x10037f43  mov     ecx, edi
0x10037f45  call    ?InternalInitialize@ThreadProcHelper@@IAEJW4ThreadProcWorkType@@PAX@Z; ThreadProcHelper::InternalInitialize(ThreadProcWorkType,void *)
0x10037f4a  mov     esi, eax
0x10037f4c  test    esi, esi
0x10037f4e  jns     short loc_10037F54
0x10037f50  push    16h
0x10037f52  jmp     short loc_10037F71
0x10037f54  mov     eax, [edi]
0x10037f56  push    ebx
0x10037f57  push    offset __GUID_0beaa6cc_1392_4e3c_b0df_51b861bd6c6e
0x10037f5c  push    edi
0x10037f5d  mov     esi, [eax]
0x10037f5f  mov     ecx, esi; this
0x10037f61  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10037f67  call    esi
0x10037f69  mov     esi, eax
0x10037f6b  test    esi, esi
0x10037f6d  jns     short loc_10037F82
0x10037f6f  push    18h
0x10037f71  mov     ecx, [ebp+4]
0x10037f74  pop     edx
0x10037f75  push    esi; void *
0x10037f76  push    offset aMultimediaDsho_3; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x10037f7b  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x10037f80  jmp     short loc_10037F84
0x10037f82  xor     esi, esi
0x10037f84  lea     ecx, [ebp+var_4]
0x10037f87  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x10037f8c  pop     edi
0x10037f8d  mov     eax, esi
0x10037f8f  pop     esi
0x10037f90  pop     ebx
0x10037f91  leave
0x10037f92  retn    4
```
