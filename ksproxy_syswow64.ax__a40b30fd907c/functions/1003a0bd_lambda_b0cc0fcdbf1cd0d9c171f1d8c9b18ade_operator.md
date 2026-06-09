# _lambda_b0cc0fcdbf1cd0d9c171f1d8c9b18ade_::operator()

- ea: `0x1003a0bd`
- end: `0x1003a16e`
- name: `_lambda_b0cc0fcdbf1cd0d9c171f1d8c9b18ade_::operator()`
- size: `177`
- prototype: `int __thiscall(int *this, int *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1003a2f0`

## callees

- `0x1000f598`
- `0x1002d510`
- `0x10037e8d`
- `0x100399ce`
- `0x10039c65`
- `0x1003a0bd`
- `0x1003abb4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1003a0fd`
- `KERNEL32!GetCurrentThreadId` at `0x1003a0fd`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1003a14d`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1003a14d`

## pseudocode

```c
int __thiscall lambda_b0cc0fcdbf1cd0d9c171f1d8c9b18ade_::operator()(int *this, int *a2, int a3)
{
  int v3; // edx
  int v5; // ebx
  int v6; // edi
  _DWORD *v7; // eax
  _DWORD *v8; // esi
  int v9; // eax
  int v10; // esi
  int v12[3]; // [esp+Ch] [ebp-18h] BYREF
  _DWORD *v13; // [esp+18h] [ebp-Ch] BYREF
  DWORD CurrentThreadId; // [esp+1Ch] [ebp-8h]
  int v15; // [esp+20h] [ebp-4h] BYREF

  v3 = *a2;
  v15 = 1;
  (*(void (__thiscall **)(_DWORD, int *, int *))(v3 + 36))(*(_DWORD *)(v3 + 36), a2, &v15);
  v5 = this[1];
  wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>::com_ptr_t<IWeakReference,wil::err_returncode_policy>(
    v12,
    this);
  v6 = v15;
  v12[1] = v5;
  v12[2] = v15;
  CurrentThreadId = GetCurrentThreadId();
  v7 = operator new(0x18u, &std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(v7);
    v9 = v12[0];
    v12[0] = 0;
    v8[3] = v9;
    v8[4] = v5;
    v8[5] = v6;
    *v8 = &off_10002014;
  }
  else
  {
    v8 = 0;
  }
  v13 = v8;
  v10 = SHTaskPoolQueueTask(0, 2, CurrentThreadId, 0, v8, 0);
  Microsoft::WRL::ComPtr<Windows::Internal::IComPoolTask>::~ComPtr<Windows::Internal::IComPoolTask>((int *)&v13);
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(v12);
  return v10;
}

```

## disassembly

```asm
0x1003a0bd  mov     edi, edi
0x1003a0bf  push    ebp
0x1003a0c0  mov     ebp, esp
0x1003a0c2  sub     esp, 18h
0x1003a0c5  mov     eax, [ebp+arg_0]
0x1003a0c8  push    ebx
0x1003a0c9  push    esi
0x1003a0ca  push    edi
0x1003a0cb  mov     edx, [eax]
0x1003a0cd  mov     edi, ecx
0x1003a0cf  lea     ecx, [ebp+var_4]
0x1003a0d2  mov     [ebp+var_4], 1
0x1003a0d9  push    ecx
0x1003a0da  push    eax
0x1003a0db  mov     esi, [edx+24h]
0x1003a0de  mov     ecx, esi; this
0x1003a0e0  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1003a0e6  call    esi
0x1003a0e8  mov     ebx, [edi+4]
0x1003a0eb  lea     ecx, [ebp+var_18]
0x1003a0ee  push    edi
0x1003a0ef  call    ??0?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@QAE@ABV01@@Z; wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>::com_ptr_t<IWeakReference,wil::err_returncode_policy>(wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> const &)
0x1003a0f4  mov     edi, [ebp+var_4]
0x1003a0f7  mov     [ebp+var_14], ebx
0x1003a0fa  mov     [ebp+var_10], edi
0x1003a0fd  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1003a103  push    offset ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1003a108  push    18h; Size
0x1003a10a  mov     [ebp+var_8], eax
0x1003a10d  call    ??2@YAPAXIABUnothrow_t@std@@@Z; operator new(uint,std::nothrow_t const &)
0x1003a112  mov     esi, eax
0x1003a114  pop     ecx
0x1003a115  pop     ecx
0x1003a116  test    esi, esi
0x1003a118  jz      short loc_1003A13C
0x1003a11a  mov     ecx, esi
0x1003a11c  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QAE@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(void)
0x1003a121  mov     eax, [ebp+var_18]
0x1003a124  mov     [ebp+var_18], 0
0x1003a12b  mov     [esi+0Ch], eax
0x1003a12e  mov     [esi+10h], ebx
0x1003a131  mov     [esi+14h], edi
0x1003a134  mov     dword ptr [esi], offset off_10002014
0x1003a13a  jmp     short loc_1003A13E
0x1003a13c  xor     esi, esi
0x1003a13e  push    0
0x1003a140  push    esi
0x1003a141  push    0
0x1003a143  push    [ebp+var_8]
0x1003a146  mov     [ebp+var_C], esi
0x1003a149  push    2
0x1003a14b  push    0
0x1003a14d  call    ds:__imp__SHTaskPoolQueueTask@24; SHTaskPoolQueueTask(x,x,x,x,x,x)
0x1003a153  lea     ecx, [ebp+var_C]
0x1003a156  mov     esi, eax
0x1003a158  call    ??1?$ComPtr@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QAE@XZ; Microsoft::WRL::ComPtr<Windows::Internal::IComPoolTask>::~ComPtr<Windows::Internal::IComPoolTask>(void)
0x1003a15d  lea     ecx, [ebp+var_18]
0x1003a160  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x1003a165  pop     edi
0x1003a166  mov     eax, esi
0x1003a168  pop     esi
0x1003a169  pop     ebx
0x1003a16a  leave
0x1003a16b  retn    8
```
