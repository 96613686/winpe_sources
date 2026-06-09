# CVPInterfaceHandler::SetDDSurfaceKernelHandles(ulong,unsigned __int64 *)

- ea: `0x180041ae0`
- end: `0x180041bb2`
- name: `?SetDDSurfaceKernelHandles@CVPInterfaceHandler@@QEAAJKPEA_K@Z`
- size: `210`
- prototype: `__int64 __fastcall(CVPInterfaceHandler *__hidden this, unsigned int, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180041bc0`

## callees

- `0x18000bde0`
- `0x180041ae0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180041b17`
- `ole32!CoTaskMemAlloc` at `0x180041b17`
- `ole32!CoTaskMemFree` at `0x180041b96`
- `ole32!CoTaskMemFree` at `0x180041b96`

## pseudocode

```c
__int64 __fastcall CVPInterfaceHandler::SetDDSurfaceKernelHandles(
        CVPInterfaceHandler *this,
        unsigned int a2,
        unsigned __int64 *a3)
{
  __int64 v3; // rbx
  DWORD v6; // ebp
  unsigned int v7; // edi
  _QWORD *v8; // rsi
  __int64 v9; // rax
  __int64 v10; // rdx
  char *m_ObjectHandle; // rcx
  _GUID v12; // xmm0
  _GUID InBuffer; // [rsp+40h] [rbp-58h] BYREF
  __int64 v15; // [rsp+50h] [rbp-48h]
  DWORD NumberOfBytesTransferred; // [rsp+A8h] [rbp+10h] BYREF

  v3 = a2;
  NumberOfBytesTransferred = 0;
  InBuffer = 0;
  v6 = 8 * a2 + 8;
  v15 = 0;
  v7 = -2147024882;
  v8 = CoTaskMemAlloc(v6);
  if ( v8 )
  {
    v9 = 0;
    if ( (_DWORD)v3 )
    {
      do
      {
        v10 = (unsigned int)(v9 + 1);
        v8[v10] = a3[v9];
        v9 = v10;
      }
      while ( (unsigned int)v10 < (unsigned int)v3 );
    }
    *v8 = v3;
    m_ObjectHandle = (char *)this->m_ObjectHandle;
    v12 = *this->m_pPropSetID;
    v15 = 0x20000000ELL;
    InBuffer = v12;
    v7 = KsSynchronousDeviceControl(m_ObjectHandle, 0x2F0003u, &InBuffer, 0x18u, v8, v6, &NumberOfBytesTransferred);
    CoTaskMemFree(v8);
  }
  return v7;
}

```

## disassembly

```asm
0x180041ae0  mov     r11, rsp
0x180041ae3  push    rbx
0x180041ae4  push    rbp
0x180041ae5  push    rsi
0x180041ae6  push    rdi
0x180041ae7  push    r14
0x180041ae9  push    r15
0x180041aeb  sub     rsp, 68h
0x180041aef  xor     eax, eax
0x180041af1  mov     ebx, edx
0x180041af3  xorps   xmm0, xmm0
0x180041af6  mov     [r11+10h], eax
0x180041afa  mov     r15, rcx
0x180041afd  mov     r14, r8
0x180041b00  movups  [rsp+98h+InBuffer], xmm0
0x180041b05  lea     ebp, ds:8[rbx*8]
0x180041b0c  mov     [r11-48h], rax
0x180041b10  mov     ecx, ebp; cb
0x180041b12  mov     edi, 8007000Eh
0x180041b17  call    cs:__imp_CoTaskMemAlloc
0x180041b1e  nop     dword ptr [rax+rax+00h]
0x180041b23  mov     rsi, rax
0x180041b26  test    rax, rax
0x180041b29  jz      short loc_180041BA2
0x180041b2b  xor     eax, eax
0x180041b2d  test    ebx, ebx
0x180041b2f  jz      short loc_180041B42
0x180041b31  lea     edx, [rax+1]
0x180041b34  mov     rax, [r14+rax*8]
0x180041b38  mov     [rsi+rdx*8], rax
0x180041b3c  mov     eax, edx
0x180041b3e  cmp     edx, ebx
0x180041b40  jb      short loc_180041B31
0x180041b42  mov     [rsi], rbx
0x180041b45  lea     r8, [rsp+98h+InBuffer]; lpInBuffer
0x180041b4a  mov     rax, [r15+68h]
0x180041b4e  mov     r9d, 18h; nInBufferSize
0x180041b54  mov     rcx, [r15+20h]; hFile
0x180041b58  mov     edx, 2F0003h; dwIoControlCode
0x180041b5d  movups  xmm0, xmmword ptr [rax]
0x180041b60  lea     rax, [rsp+98h+NumberOfBytesTransferred]
0x180041b68  mov     [rsp+98h+var_48], 0Eh
0x180041b70  mov     [rsp+98h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x180041b75  mov     [rsp+98h+var_70], ebp; DWORD
0x180041b79  mov     [rsp+98h+var_78], rsi; LPVOID
0x180041b7e  movdqu  [rsp+98h+InBuffer], xmm0
0x180041b84  mov     [rsp+98h+var_44], 2
0x180041b8c  call    KsSynchronousDeviceControl
0x180041b91  mov     rcx, rsi; pv
0x180041b94  mov     edi, eax
0x180041b96  call    cs:__imp_CoTaskMemFree
0x180041b9d  nop     dword ptr [rax+rax+00h]
0x180041ba2  mov     eax, edi
0x180041ba4  add     rsp, 68h
0x180041ba8  pop     r15
0x180041baa  pop     r14
0x180041bac  pop     rdi
0x180041bad  pop     rsi
0x180041bae  pop     rbp
0x180041baf  pop     rbx
0x180041bb0  retn
```
