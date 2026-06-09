# CVPInterfaceHandler::SetDDSurfaceKernelHandles(ulong,ulong *)

- ea: `0x100360ee`
- end: `0x10036181`
- name: `?SetDDSurfaceKernelHandles@CVPInterfaceHandler@@QAEJKPAK@Z`
- size: `147`
- prototype: `int __thiscall(CVPInterfaceHandler *__hidden this, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x100357f0`

## callees

- `0x1001f3b0`
- `0x100360ee`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x10036116`
- `ole32!CoTaskMemAlloc` at `0x10036116`
- `ole32!CoTaskMemFree` at `0x10036172`
- `ole32!CoTaskMemFree` at `0x10036172`

## pseudocode

```c
int __thiscall CVPInterfaceHandler::SetDDSurfaceKernelHandles(
        CVPInterfaceHandler *this,
        unsigned int a2,
        unsigned int *a3)
{
  int v3; // edi
  _DWORD *v4; // ebx
  unsigned int i; // ecx
  CVPInterfaceHandler *v6; // eax
  const _GUID *m_pPropSetID; // esi
  void *m_ObjectHandle; // [esp-1Ch] [ebp-4Ch]
  _DWORD InBuffer[6]; // [esp+Ch] [ebp-24h] BYREF
  DWORD nOutBufferSize; // [esp+24h] [ebp-Ch]
  DWORD BytesReturned; // [esp+28h] [ebp-8h] BYREF
  CVPInterfaceHandler *v13; // [esp+2Ch] [ebp-4h]

  v13 = this;
  v3 = -2147024882;
  BytesReturned = 0;
  nOutBufferSize = 4 * a2 + 4;
  v4 = CoTaskMemAlloc(nOutBufferSize);
  if ( v4 )
  {
    for ( i = 0; i < a2; ++i )
      v4[i + 1] = a3[i];
    v6 = v13;
    *v4 = a2;
    m_pPropSetID = v6->m_pPropSetID;
    InBuffer[0] = m_pPropSetID->Data1;
    m_pPropSetID = (const _GUID *)((char *)m_pPropSetID + 4);
    m_ObjectHandle = v6->m_ObjectHandle;
    InBuffer[1] = m_pPropSetID->Data1;
    m_pPropSetID = (const _GUID *)((char *)m_pPropSetID + 4);
    InBuffer[2] = m_pPropSetID->Data1;
    InBuffer[3] = *(_DWORD *)&m_pPropSetID->Data2;
    InBuffer[4] = 14;
    InBuffer[5] = 2;
    v3 = KsSynchronousDeviceControl(m_ObjectHandle, 0x2F0003u, InBuffer, 0x18u, v4, nOutBufferSize, &BytesReturned);
    CoTaskMemFree(v4);
  }
  return v3;
}

```

## disassembly

```asm
0x100360ee  mov     edi, edi
0x100360f0  push    ebp
0x100360f1  mov     ebp, esp
0x100360f3  sub     esp, 24h
0x100360f6  push    ebx
0x100360f7  push    esi
0x100360f8  mov     esi, [ebp+arg_0]
0x100360fb  push    edi
0x100360fc  mov     [ebp+var_4], ecx
0x100360ff  mov     edi, 8007000Eh
0x10036104  mov     [ebp+BytesReturned], 0
0x1003610b  lea     eax, ds:4[esi*4]
0x10036112  push    eax; cb
0x10036113  mov     [ebp+nOutBufferSize], eax
0x10036116  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1003611c  mov     ebx, eax
0x1003611e  test    ebx, ebx
0x10036120  jz      short loc_10036178
0x10036122  xor     ecx, ecx
0x10036124  test    esi, esi
0x10036126  jz      short loc_10036137
0x10036128  mov     eax, [ebp+arg_4]
0x1003612b  mov     eax, [eax+ecx*4]
0x1003612e  mov     [ebx+ecx*4+4], eax
0x10036132  inc     ecx
0x10036133  cmp     ecx, esi
0x10036135  jb      short loc_10036128
0x10036137  mov     eax, [ebp+var_4]
0x1003613a  lea     edi, [ebp+InBuffer]
0x1003613d  mov     [ebx], esi
0x1003613f  lea     ecx, [ebp+BytesReturned]
0x10036142  push    ecx; lpBytesReturned
0x10036143  push    [ebp+nOutBufferSize]; nOutBufferSize
0x10036146  mov     esi, [eax+34h]
0x10036149  lea     ecx, [ebp+InBuffer]
0x1003614c  push    ebx; lpOutBuffer
0x1003614d  push    18h; nInBufferSize
0x1003614f  push    ecx; lpInBuffer
0x10036150  movsd
0x10036151  push    2F0003h; dwIoControlCode
0x10036156  push    dword ptr [eax+10h]; hDevice
0x10036159  movsd
0x1003615a  movsd
0x1003615b  movsd
0x1003615c  mov     [ebp+var_14], 0Eh
0x10036163  mov     [ebp+var_10], 2
0x1003616a  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x1003616f  push    ebx; pv
0x10036170  mov     edi, eax
0x10036172  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10036178  mov     eax, edi
0x1003617a  pop     edi
0x1003617b  pop     esi
0x1003617c  pop     ebx
0x1003617d  leave
0x1003617e  retn    8
```
