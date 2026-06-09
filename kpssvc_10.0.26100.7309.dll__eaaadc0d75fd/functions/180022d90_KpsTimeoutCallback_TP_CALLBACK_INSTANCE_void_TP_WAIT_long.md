# KpsTimeoutCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180022d90`
- end: `0x180022e47`
- name: `?KpsTimeoutCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `183`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180022d90`
- `0x180026404`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180022dbf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180022dbf`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180022e22`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180022e22`
- `ntdll!RtlLeaveCriticalSection` at `0x180022e3b`
- `ntdll!RtlEnterCriticalSection` at `0x180022da7`
- `ntdll!RtlEnterCriticalSection` at `0x180022da7`
- `HTTPAPI!HttpCancelHttpRequest` at `0x180022e05`
- `HTTPAPI!HttpCancelHttpRequest` at `0x180022e05`

## pseudocode

```c
void __fastcall KpsTimeoutCallback(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  char IsEnabled; // al
  int v7; // ecx

  v4 = (struct _RTL_CRITICAL_SECTION *)(Context + 288);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(Context + 288));
  SetThreadpoolWait(*((PTP_WAIT *)Context + 41), 0, 0);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_3749982522>::GetImpl'::`2'::impl);
  v7 = *((_DWORD *)Context + 84);
  *((_DWORD *)Context + 84) = 0;
  if ( !IsEnabled )
  {
    if ( v7 != 1 )
      goto LABEL_7;
LABEL_6:
    CancelIoEx(*((HANDLE *)Context + 27), (LPOVERLAPPED)Context);
    goto LABEL_7;
  }
  if ( v7 == 1 )
    goto LABEL_6;
  if ( v7 == 2 )
    HttpCancelHttpRequest(RequestQueueHandle, *(_QWORD *)(*((_QWORD *)Context + 7) + 16LL), 0);
LABEL_7:
  RtlLeaveCriticalSection(v4);
}

```

## disassembly

```asm
0x180022d90  mov     [rsp+arg_0], rbx
0x180022d95  push    rdi
0x180022d96  sub     rsp, 20h
0x180022d9a  lea     rdi, [rdx+120h]
0x180022da1  mov     rbx, rdx
0x180022da4  mov     rcx, rdi; CriticalSection
0x180022da7  call    cs:__imp_RtlEnterCriticalSection
0x180022dae  nop     dword ptr [rax+rax+00h]
0x180022db3  mov     rcx, [rbx+148h]; pwa
0x180022dba  xor     r8d, r8d; pftTimeout
0x180022dbd  xor     edx, edx; h
0x180022dbf  call    cs:__imp_SetThreadpoolWait
0x180022dc6  nop     dword ptr [rax+rax+00h]
0x180022dcb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_3749982522@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522> `wil::Feature<__WilFeatureTraits_Feature_3749982522>::GetImpl(void)'::`2'::impl
0x180022dd2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::__private_IsEnabled(void)
0x180022dd7  mov     ecx, [rbx+150h]
0x180022ddd  xor     edx, edx
0x180022ddf  mov     [rbx+150h], edx
0x180022de5  test    al, al
0x180022de7  jz      short loc_180022E13
0x180022de9  cmp     ecx, 1
0x180022dec  jz      short loc_180022E18
0x180022dee  cmp     ecx, 2
0x180022df1  jnz     short loc_180022E2E
0x180022df3  mov     rdx, [rbx+38h]
0x180022df7  xor     r8d, r8d; Overlapped
0x180022dfa  mov     rcx, cs:RequestQueueHandle; RequestQueueHandle
0x180022e01  mov     rdx, [rdx+10h]; RequestId
0x180022e05  call    cs:__imp_HttpCancelHttpRequest
0x180022e0c  nop     dword ptr [rax+rax+00h]
0x180022e11  jmp     short loc_180022E2E
0x180022e13  cmp     ecx, 1
0x180022e16  jnz     short loc_180022E2E
0x180022e18  mov     rcx, [rbx+0D8h]; hFile
0x180022e1f  mov     rdx, rbx; lpOverlapped
0x180022e22  call    cs:__imp_CancelIoEx
0x180022e29  nop     dword ptr [rax+rax+00h]
0x180022e2e  mov     rcx, rdi
0x180022e31  mov     rbx, [rsp+28h+arg_0]
0x180022e36  add     rsp, 20h
0x180022e3a  pop     rdi
0x180022e3b  jmp     cs:__imp_RtlLeaveCriticalSection
```
