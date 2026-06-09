# win_musl::FiberStream<win_musl::FiberStreamClient<win_musl::consumption::ContainerPartSender,win_scope::scope<win_musl::consumption::ContainerPartSender *,win_scope::const_policies<win_scope::com_policies>>>>::TransferToFiber(void)

- ea: `0x1800044c0`
- end: `0x1800045ef`
- name: `?TransferToFiber@?$FiberStream@V?$FiberStreamClient@VContainerPartSender@consumption@win_musl@@V?$scope@PEAVContainerPartSender@consumption@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@win_musl@@@win_musl@@AEAAXXZ`
- size: `303`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800040b8`
- `0x1800eaed8`

## callees

- `0x180001de4`
- `0x1800044c0`
- `0x1800045f8`
- `0x180004680`
- `0x180015660`
- `0x180031218`
- `0x1800693bc`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000455a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000455a`

## string_xrefs

- `0x180004553`: `win_musl::FiberStream<class win_musl::FiberStreamClient<class win_musl::consumption::ContainerPartSender,class win_scope::scope<class win_musl::consumption::ContainerPartSender *,struct win_scope::const_policies<struct win_scope::com_policies> > > >::TransferToFiber, m_pCommandDerecurser->IsRecursed() is true, must call command syncronously for the data copy to work!\n`

## pseudocode

```c

```
