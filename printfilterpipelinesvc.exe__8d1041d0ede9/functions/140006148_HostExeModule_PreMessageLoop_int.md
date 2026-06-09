# HostExeModule::PreMessageLoop(int)

- ea: `0x140006148`
- end: `0x1400063c3`
- name: `?PreMessageLoop@HostExeModule@@QEAAJH@Z`
- size: `635`
- prototype: `__int64 __fastcall(HostExeModule *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140007214`

## callees

- `0x1400051d8`
- `0x140005358`
- `0x140005470`
- `0x140006148`
- `0x1400071e8`
- `0x140007ce0`
- `0x140063010`

## import_xrefs

- `KERNEL32!CreateThread` at `0x140006249`
- `KERNEL32!CreateThread` at `0x140006249`
- `KERNEL32!CreateEventW` at `0x140006207`
- `KERNEL32!CreateEventW` at `0x140006207`
- `KERNEL32!WaitForSingleObject` at `0x1400062f1`
- `KERNEL32!WaitForSingleObject` at `0x1400062f1`
- `KERNEL32!SetEvent` at `0x1400062d8`
- `KERNEL32!SetEvent` at `0x1400062d8`
- `KERNEL32!CloseHandle` at `0x14000625e`
- `KERNEL32!CloseHandle` at `0x14000625e`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1400062ad`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1400062ad`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000633e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000633e`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x1400062c5`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x140006303`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x1400062c5`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x140006303`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HostExeModule::PreMessageLoop(HostExeModule *this, DWORD a2)
{
  PVOID *v2; // rcx
  HRESULT LastErrorAsHResult; // ebx
  HANDLE v4; // rbx
  NCoreLibrary *v5; // rcx
  void *v6; // rdi
  HRESULT v7; // eax
  struct ATL::_ATL_OBJMAP_ENTRY30 **v8; // rdi
  __int64 *v9; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v10; // rdx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF
  DWORD ThreadId; // [rsp+48h] [rbp+10h] BYREF

  ThreadId = a2;
  ppv = this;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        &WPP_6c5a4e2d3143381cd824abab71c4788e_Traceguids,
        (unsigned __int8)byte_140080E48);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 7) & 0x100) != 0 )
      WPP_SF_d(v2[2], 13, &WPP_6c5a4e2d3143381cd824abab71c4788e_Traceguids, dwMilliseconds);
  }
  LastErrorAsHResult = ATL::AtlComModuleRegisterClassObjects(
                         (struct ATL::_ATL_COM_MODULE70 *)v2,
                         a2,
                         (byte_140080E48 != 0) + 4);
  if ( LastErrorAsHResult < 0 )
  {
    byte_140080E40 = 0;
  }
  else
  {
    if ( byte_140080E40 )
    {
      ppv = (LPVOID)-1LL;
      hEvent = CreateEventW(0, 0, 0, 0);
      if ( hEvent )
      {
        ThreadId = 0;
        v4 = CreateThread(0, 0, ATL::CAtlExeModuleT<HostExeModule>::MonitorProc, &_AtlModule, 0, &ThreadId);
        if ( !v4 )
          CloseHandle(hEvent);
      }
      else
      {
        v4 = 0;
      }
      NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(&ppv, v4);
      v6 = ppv;
      if ( ppv == (LPVOID)-1LL && (LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v5), LastErrorAsHResult < 0) )
      {
        v7 = 0;
        v8 = off_140080210;
        v9 = off_140080218;
        while ( v8 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v9 && !v7 )
        {
          v10 = *v8;
          if ( *v8 && *((_DWORD *)v10 + 10) )
          {
            v7 = CoRevokeClassObject(*((_DWORD *)v10 + 10));
            v9 = off_140080218;
          }
          ++v8;
        }
      }
      else
      {
        LastErrorAsHResult = CoResumeClassObjects();
        if ( LastErrorAsHResult < 0 )
        {
          SetEvent(hEvent);
          if ( v6 == (void *)-1LL )
            v6 = 0;
          WaitForSingleObject(v6, dwMilliseconds);
        }
      }
      NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&ppv);
    }
    else
    {
      LastErrorAsHResult = CoResumeClassObjects();
    }
    if ( LastErrorAsHResult >= 0 )
    {
      ppv = 0;
      LastErrorAsHResult = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &IID_IGlobalOptions, &ppv);
      if ( LastErrorAsHResult < 0
        || (LastErrorAsHResult = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(
                                   ppv,
                                   1,
                                   1),
            LastErrorAsHResult < 0) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            &WPP_6c5a4e2d3143381cd824abab71c4788e_Traceguids,
            (unsigned int)LastErrorAsHResult);
      }
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  return (unsigned int)LastErrorAsHResult;
}

```

## disassembly

```asm
0x140006148  mov     rax, rsp
0x14000614b  mov     [rax+18h], rbx
0x14000614f  mov     [rax+20h], rbp
0x140006153  mov     [rax+10h], edx
0x140006156  mov     [rax+8], rcx
0x14000615a  push    rdi
0x14000615b  sub     rsp, 30h
0x14000615f  lea     rbp, WPP_GLOBAL_Control
0x140006166  mov     rcx, cs:WPP_GLOBAL_Control
0x14000616d  cmp     rcx, rbp
0x140006170  jz      short loc_1400061C6
0x140006172  mov     ebx, 100h
0x140006177  test    [rcx+1Ch], ebx
0x14000617a  jz      short loc_1400061A0
0x14000617c  movzx   r9d, cs:byte_140080E48
0x140006184  mov     edx, 0Ch
0x140006189  lea     r8, WPP_6c5a4e2d3143381cd824abab71c4788e_Traceguids
0x140006190  mov     rcx, [rcx+10h]
0x140006194  call    WPP_SF_d
0x140006199  mov     rcx, cs:WPP_GLOBAL_Control
0x1400061a0  cmp     rcx, rbp
0x1400061a3  jz      short loc_1400061C6
0x1400061a5  test    [rcx+1Ch], ebx
0x1400061a8  jz      short loc_1400061C6
0x1400061aa  mov     edx, 0Dh
0x1400061af  mov     r9d, cs:dwMilliseconds
0x1400061b6  lea     r8, WPP_6c5a4e2d3143381cd824abab71c4788e_Traceguids
0x1400061bd  mov     rcx, [rcx+10h]
0x1400061c1  call    WPP_SF_d
0x1400061c6  mov     al, cs:byte_140080E48
0x1400061cc  neg     al
0x1400061ce  sbb     r8d, r8d
0x1400061d1  neg     r8d
0x1400061d4  add     r8d, 4; unsigned int
0x1400061d8  call    ?AtlComModuleRegisterClassObjects@ATL@@YAJPEAU_ATL_COM_MODULE70@1@KK@Z; ATL::AtlComModuleRegisterClassObjects(ATL::_ATL_COM_MODULE70 *,ulong,ulong)
0x1400061dd  mov     ebx, eax
0x1400061df  test    eax, eax
0x1400061e1  js      loc_1400063AA
0x1400061e7  cmp     cs:byte_140080E40, 0
0x1400061ee  jz      loc_140006303
0x1400061f4  mov     [rsp+38h+ppv], 0FFFFFFFFFFFFFFFFh
0x1400061fd  xor     r9d, r9d; lpName
0x140006200  xor     r8d, r8d; bInitialState
0x140006203  xor     edx, edx; bManualReset
0x140006205  xor     ecx, ecx; lpEventAttributes
0x140006207  call    cs:__imp_CreateEventW
0x14000620d  mov     cs:hEvent, rax
0x140006214  test    rax, rax
0x140006217  jnz     short loc_14000621D
0x140006219  xor     ebx, ebx
0x14000621b  jmp     short loc_140006264
0x14000621d  mov     [rsp+38h+ThreadId], 0
0x140006225  lea     rax, [rsp+38h+ThreadId]
0x14000622a  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x14000622f  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x140006237  lea     r9, ?_AtlModule@@3VHostExeModule@@A; lpParameter
0x14000623e  lea     r8, ?MonitorProc@?$CAtlExeModuleT@VHostExeModule@@@ATL@@SAKPEAX@Z; lpStartAddress
0x140006245  xor     edx, edx; dwStackSize
0x140006247  xor     ecx, ecx; lpThreadAttributes
0x140006249  call    cs:__imp_CreateThread
0x14000624f  mov     rbx, rax
0x140006252  test    rax, rax
0x140006255  jnz     short loc_140006264
0x140006257  mov     rcx, cs:hEvent; hObject
0x14000625e  call    cs:__imp_CloseHandle
0x140006264  mov     rdx, rbx
0x140006267  lea     rcx, [rsp+38h+ppv]
0x14000626c  call    ?Attach@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXPEAX@Z; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(void *)
0x140006271  mov     rdi, [rsp+38h+ppv]
0x140006276  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14000627a  jnz     short loc_1400062C5
0x14000627c  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x140006281  mov     ebx, eax
0x140006283  test    eax, eax
0x140006285  jns     short loc_1400062C5
0x140006287  xor     eax, eax
0x140006289  mov     rdi, cs:off_140080210
0x140006290  mov     rcx, cs:off_140080218
0x140006297  jmp     short loc_1400062BE
0x140006299  test    eax, eax
0x14000629b  jnz     short loc_1400062F7
0x14000629d  mov     rdx, [rdi]
0x1400062a0  test    rdx, rdx
0x1400062a3  jz      short loc_1400062BA
0x1400062a5  cmp     [rdx+28h], eax
0x1400062a8  jz      short loc_1400062BA
0x1400062aa  mov     ecx, [rdx+28h]; dwRegister
0x1400062ad  call    cs:__imp_CoRevokeClassObject
0x1400062b3  mov     rcx, cs:off_140080218
0x1400062ba  add     rdi, 8
0x1400062be  cmp     rdi, rcx
0x1400062c1  jb      short loc_140006299
0x1400062c3  jmp     short loc_1400062F7
0x1400062c5  call    cs:__imp_CoResumeClassObjects
0x1400062cb  mov     ebx, eax
0x1400062cd  test    eax, eax
0x1400062cf  jns     short loc_1400062F7
0x1400062d1  mov     rcx, cs:hEvent; hEvent
0x1400062d8  call    cs:__imp_SetEvent
0x1400062de  xor     eax, eax
0x1400062e0  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400062e4  cmovz   rdi, rax
0x1400062e8  mov     edx, cs:dwMilliseconds; dwMilliseconds
0x1400062ee  mov     rcx, rdi; hHandle
0x1400062f1  call    cs:__imp_WaitForSingleObject
0x1400062f7  lea     rcx, [rsp+38h+ppv]
0x1400062fc  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x140006301  jmp     short loc_14000630B
0x140006303  call    cs:__imp_CoResumeClassObjects
0x140006309  mov     ebx, eax
0x14000630b  test    ebx, ebx
0x14000630d  js      loc_1400063B1
0x140006313  mov     [rsp+38h+ppv], 0
0x14000631c  lea     rax, [rsp+38h+ppv]
0x140006321  mov     qword ptr [rsp+38h+dwCreationFlags], rax; ppv
0x140006326  lea     r9, IID_IGlobalOptions; riid
0x14000632d  mov     edi, 1
0x140006332  mov     r8d, edi; dwClsContext
0x140006335  xor     edx, edx; pUnkOuter
0x140006337  lea     rcx, CLSID_GlobalOptions; rclsid
0x14000633e  call    cs:__imp_CoCreateInstance
0x140006344  mov     ebx, eax
0x140006346  test    eax, eax
0x140006348  js      short loc_140006366
0x14000634a  mov     rcx, [rsp+38h+ppv]
0x14000634f  mov     rax, [rcx]
0x140006352  mov     r8d, edi
0x140006355  mov     edx, edi
0x140006357  mov     rax, [rax+18h]
0x14000635b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006360  mov     ebx, eax
0x140006362  test    eax, eax
0x140006364  jns     short loc_140006391
0x140006366  mov     rcx, cs:WPP_GLOBAL_Control
0x14000636d  cmp     rcx, rbp
0x140006370  jz      short loc_140006391
0x140006372  test    byte ptr [rcx+1Ch], 2
0x140006376  jz      short loc_140006391
0x140006378  mov     edx, 0Eh
0x14000637d  mov     r9d, ebx
0x140006380  lea     r8, WPP_6c5a4e2d3143381cd824abab71c4788e_Traceguids
0x140006387  mov     rcx, [rcx+10h]
0x14000638b  call    WPP_SF_d
0x140006390  nop
0x140006391  mov     rcx, [rsp+38h+ppv]
0x140006396  test    rcx, rcx
0x140006399  jz      short loc_1400063A8
0x14000639b  mov     rax, [rcx]
0x14000639e  mov     rax, [rax+10h]
0x1400063a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400063a7  nop
0x1400063a8  jmp     short loc_1400063B1
0x1400063aa  mov     cs:byte_140080E40, 0
0x1400063b1  mov     eax, ebx
0x1400063b3  mov     rbx, [rsp+38h+arg_10]
0x1400063b8  mov     rbp, [rsp+38h+arg_18]
0x1400063bd  add     rsp, 30h
0x1400063c1  pop     rdi
0x1400063c2  retn
```
