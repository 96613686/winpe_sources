# ClusNode::~ClusNode(void)

- ea: `0x180031eb4`
- end: `0x180031f6b`
- name: `??1ClusNode@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ClusNode *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180032718`

## callees

- `0x180029578`
- `0x180031eb4`
- `0x180033190`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180031eda`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180031efc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180031f1e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180031f3d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180031eda`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180031efc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180031f1e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180031f3d`

## pseudocode

```c
void __fastcall ClusNode::~ClusNode(ClusNode *this)
{
  SC_HANDLE v2; // rcx
  SC_HANDLE v3; // rcx
  SC_HANDLE v4; // rcx
  SC_HANDLE v5; // rcx

  cxl::AutoHandle<HKEY__ *,long,&long RegCloseKey(HKEY__ *),0>::Close((char *)this + 232);
  v2 = (SC_HANDLE)*((_QWORD *)this + 18);
  if ( (unsigned __int64)v2 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseServiceHandle(v2);
    *((_QWORD *)this + 18) = 0;
  }
  v3 = (SC_HANDLE)*((_QWORD *)this + 17);
  if ( (unsigned __int64)v3 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseServiceHandle(v3);
    *((_QWORD *)this + 17) = 0;
  }
  v4 = (SC_HANDLE)*((_QWORD *)this + 16);
  if ( (unsigned __int64)v4 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseServiceHandle(v4);
    *((_QWORD *)this + 16) = 0;
  }
  v5 = (SC_HANDLE)*((_QWORD *)this + 15);
  if ( (unsigned __int64)v5 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseServiceHandle(v5);
    *((_QWORD *)this + 15) = 0;
  }
  std::wstring::_Tidy_deallocate((char *)this + 80);
  std::wstring::_Tidy_deallocate((char *)this + 48);
  std::wstring::_Tidy_deallocate((char *)this + 16);
}

```

## disassembly

```asm
0x180031eb4  push    rbx
0x180031eb6  sub     rsp, 20h
0x180031eba  mov     rbx, rcx
0x180031ebd  add     rcx, 0E8h
0x180031ec4  call    ?Close@?$AutoHandle@PEAUHKEY__@@J$1?RegCloseKey@@YAJPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<HKEY__ *,long,&RegCloseKey(HKEY__ *),0>::Close(void)
0x180031ec9  mov     rcx, [rbx+90h]; hSCObject
0x180031ed0  lea     rax, [rcx-1]
0x180031ed4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180031ed8  ja      short loc_180031EEB
0x180031eda  call    cs:__imp_CloseServiceHandle
0x180031ee0  mov     qword ptr [rbx+90h], 0
0x180031eeb  mov     rcx, [rbx+88h]; hSCObject
0x180031ef2  lea     rax, [rcx-1]
0x180031ef6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180031efa  ja      short loc_180031F0D
0x180031efc  call    cs:__imp_CloseServiceHandle
0x180031f02  mov     qword ptr [rbx+88h], 0
0x180031f0d  mov     rcx, [rbx+80h]; hSCObject
0x180031f14  lea     rax, [rcx-1]
0x180031f18  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180031f1c  ja      short loc_180031F2F
0x180031f1e  call    cs:__imp_CloseServiceHandle
0x180031f24  mov     qword ptr [rbx+80h], 0
0x180031f2f  mov     rcx, [rbx+78h]; hSCObject
0x180031f33  lea     rax, [rcx-1]
0x180031f37  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180031f3b  ja      short loc_180031F4B
0x180031f3d  call    cs:__imp_CloseServiceHandle
0x180031f43  mov     qword ptr [rbx+78h], 0
0x180031f4b  lea     rcx, [rbx+50h]
0x180031f4f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031f54  lea     rcx, [rbx+30h]
0x180031f58  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031f5d  lea     rcx, [rbx+10h]
0x180031f61  add     rsp, 20h
0x180031f65  pop     rbx
0x180031f66  jmp     ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
